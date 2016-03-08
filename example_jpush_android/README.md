# Welcome to your Appcelerator Titanium Mobile Project

``` java
if (running_activity_name.equals("org.appcelerator.titanium.TiActivity")){
        	if (JPushInterface.ACTION_NOTIFICATION_RECEIVED.equals(intent.getAction())){
	        	Intent intent2 = new Intent();
	            intent2.setAction("ACTION_NOTIFICATION");
	        	intent2.putExtras(intent.getExtras());
	            
	            context.sendBroadcast(intent2);
	        }
        	
//        	if (JPushInterface.ACTION_MESSAGE_RECEIVED.equals(intent.getAction()) ||
//	        		JPushInterface.ACTION_NOTIFICATION_OPENED.equals(intent.getAction())){
//	        	Intent intent2 = new Intent();
//	            intent2.setAction("ACTION_MESSAGE");
//	        	intent2.putExtras(intent.getExtras());
//	            
//	            context.sendBroadcast(intent2);
//	        }
        	if (JPushInterface.ACTION_MESSAGE_RECEIVED.equals(intent.getAction())){
        		Intent intent2 = new Intent();
        		intent2.setAction("ACTION_MESSAGE");
        		intent2.putExtras(intent.getExtras());
        		
        		context.sendBroadcast(intent2);
        	}
        	if (JPushInterface.ACTION_NOTIFICATION_OPENED.equals(intent.getAction())){
        		Intent intent2 = new Intent();
        		intent2.setAction("ACTION_NOTIFICATION_OPENED");
        		intent2.putExtras(intent.getExtras());
        		
        		context.sendBroadcast(intent2);
        	}
        }
        else{
        	if (JPushInterface.ACTION_NOTIFICATION_OPENED.equals(intent.getAction())){
	        	PackageManager pm = context.getPackageManager();
    			Intent intent2 = pm.getLaunchIntentForPackage(context.getPackageName());
    			intent2.putExtras(intent.getExtras());
    			context.startActivity(intent2);
    			System.out.println("~~~~~~~~~~~\n" + context.getPackageName()+ "\n~~~~~~~~~~~");
    			System.out.println("~~~~~~~~~~~\nsend intent args\n~~~~~~~~~~~");
	        	Intent intent3 = new Intent();
	            intent3.setAction("ACTION_NOTIFICATION_OPENED");
	        	intent3.putExtras(intent.getExtras());
	            
	            context.sendBroadcast(intent3);

	        	return;
	        }
        }
```
