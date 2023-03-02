# Plugin Registration

In the last chapter, we created a sample plugin to create a follow-up Task activity when a Contact record is created. In this chapter, we will see how to register this plugin in CRM using Plugin Registration Tool. You can find the tool at this location: SDK/Tools/PluginRegistration/PluginRegistration.exe.

For convenience, the plugin registration process is divided into three sections −

*   Connecting to the Server
*   Registering the Assembly
*   Registering the Plugin

Connecting to the Server
------------------------

**Step 1** − Run the **PluginRegistration.exe** from the location specified earlier. Click the Create New Connection button.

![Mscrm Plugin Registration New Connection](./Plugins/mscrm_plugin_registration_new_connection.jpg)

**Step 2** − In the Login window, choose Office 365 since we are using the online version of CRM. Enter your credentials and click Login.

![Mscrm Plugin Registration Login](./Plugins/mscrm_plugin_registration_login.jpg)

**Step 3** − The tool will open and look like the following screenshot.

![Mscrm Plugin Registration Assembly List](./Plugins/mscrm_plugin_registration_assembly_list.jpg)

Registering the Assembly
------------------------

**Step 1** − Go to Register → Register New Assembly.

![Mscrm Plugin Registration Assembly](./Plugins/mscrm_plugin_registration_assembly.jpg)

**Step 2** − This will open the Register New Assembly window. Click the Navigate icon and locate the Plugin DLL that you created in the last chapter.

![Mscrm Plugin Registration Load Assembly](./Plugins/mscrm_plugin_registration_load_assembly.jpg)

**Step 3** − After navigating the DLL, click Load Assembly. This will populate the SamplePlugins assembly and all its plugin classes. You can see the **PostCreateContact** plugin class highlighted below. If your plugin assembly had 3 plugin classes, it would have shown three plugins listed there.

![Mscrm Plugin Registration New Assembly 2](./Plugins/mscrm_plugin_registration_new_assembly_2.jpg)

**Step 4** − Select Isolation Mode as Sandbox, Location as Database and click Register Selected Plugins. It will show you a success message, if the registration is successful.

Registering the Plugin
----------------------

Now we will be registering the specific steps on which the individual plugins will be called.

**Step 1** − Select the PostCreateContact plugin.

![Mscrm Plugin Step Select Plugin](./Plugins/mscrm_plugin_step_select_plugin.jpg)

**Step 2** − Click Register → Register New Step.

![Mscrm Plugin Step Register New Step](./Plugins/mscrm_plugin_step_register_new_step.jpg)

**Step 3** − We will be registering this plugin on the creation of the Contact entity, on postoperation stage and in the synchronous mode.

**Message** − Create

**Primary Entity** − Contact

**Event Pipeline Stage of Execution** − Post-operation

**Execution Mode** − Synchronous

Keep the rest of the options by default and click Register New Step.

![Mscrm Plugin Step Register New Step Details ](./Plugins/mscrm_plugin_step_register_new_step_details.jpg)

You can see a new step added to the plugin.

![MScrm Plugin Step Added Step](./Plugins/mscrm_plugin_step_added_step.jpg)

Now we will go to CRM and test if our plugin is working correctly. Note that these test steps are specific to our example plugin.

Testing the Plugin
------------------

Go to Contacts tab and create a new record. Once you save the record, you can see a new activity created and associated with this record.

![Mscrm Plugin Create Contact](./Plugins/mscrm_plugin_create_contact.jpg)

You can click the activity to see the details that we had set in the code.

![Mscrm Plugin Created Activity](./Plugins/mscrm_plugin_created_activity.jpg)

This confirms that our plugin ran successfully. Similarly, you can extend your plugins to achieve highly complex functionalities.

[Previous Page](./Plugins.md)  [Next Page](./Web%20Services.md) 