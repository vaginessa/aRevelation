# Bugs
* Open multiple files and hit back -> white screen
  * Reason: revelation entry group id "b5a0040f-e7bd-4314-b065-5f10be276730" (e.g.) from file b is not in file a
  * Exception:
```
W/System.err: java.lang.Exception: Cannot find group with id = b5a0040f-e7bd-4314-b065-5f10be276730
W/System.err:     at com.github.marmaladesky.data.RevelationData.getEntryGroupById(RevelationData.java:107)
W/System.err:     at com.github.marmaladesky.RevelationBrowserFragment.onCreateView(RevelationBrowserFragment.java:43)
W/System.err:     at android.app.Fragment.performCreateView(Fragment.java:2353)
W/System.err:     at android.app.FragmentManagerImpl.moveToState(FragmentManager.java:995)
W/System.err:     at android.app.FragmentManagerImpl.moveToState(FragmentManager.java:1171)
W/System.err:     at android.app.BackStackRecord.popFromBackStack(BackStackRecord.java:1750)
W/System.err:     at android.app.FragmentManagerImpl.popBackStackState(FragmentManager.java:1637)
W/System.err:     at android.app.FragmentManagerImpl.popBackStackImmediate(FragmentManager.java:579)
W/System.err:     at android.app.Activity.onBackPressed(Activity.java:2752)
W/System.err:     at android.support.v4.app.FragmentActivity.onBackPressed(FragmentActivity.java:175)
W/System.err:     at com.github.marmaladesky.ARevelation.onBackPressed(ARevelation.java:178)
W/System.err:     at android.app.Activity.onKeyUp(Activity.java:2726)
W/System.err:     at android.view.KeyEvent.dispatch(KeyEvent.java:2717)
W/System.err:     at android.app.Activity.dispatchKeyEvent(Activity.java:3030)
W/System.err:     at android.support.v7.app.AppCompatActivity.dispatchKeyEvent(AppCompatActivity.java:534)
W/System.err:     at android.support.v7.view.WindowCallbackWrapper.dispatchKeyEvent(WindowCallbackWrapper.java:58)
W/System.err:     at android.support.v7.app.AppCompatDelegateImplBase$AppCompatWindowCallbackBase.dispatchKeyEvent(AppCompatDelegateImplBase.java:316)
W/System.err:     at com.android.internal.policy.DecorView.dispatchKeyEvent(DecorView.java:322)
W/System.err:     at android.view.ViewRootImpl$ViewPostImeInputStage.processKeyEvent(ViewRootImpl.java:4337)
W/System.err:     at android.view.ViewRootImpl$ViewPostImeInputStage.onProcess(ViewRootImpl.java:4308)
W/System.err:     at android.view.ViewRootImpl$InputStage.deliver(ViewRootImpl.java:3859)
W/System.err:     at android.view.ViewRootImpl$InputStage.onDeliverToNext(ViewRootImpl.java:3912)
W/System.err:     at android.view.ViewRootImpl$InputStage.forward(ViewRootImpl.java:3878)
W/System.err:     at android.view.ViewRootImpl$AsyncInputStage.forward(ViewRootImpl.java:4005)
W/System.err:     at android.view.ViewRootImpl$InputStage.apply(ViewRootImpl.java:3886)
W/System.err:     at android.view.ViewRootImpl$AsyncInputStage.apply(ViewRootImpl.java:4062)
W/System.err:     at android.view.ViewRootImpl$InputStage.deliver(ViewRootImpl.java:3859)
W/System.err:     at android.view.ViewRootImpl$InputStage.onDeliverToNext(ViewRootImpl.java:3912)
W/System.err:     at android.view.ViewRootImpl$InputStage.forward(ViewRootImpl.java:3878)
W/System.err:     at android.view.ViewRootImpl$InputStage.apply(ViewRootImpl.java:3886)
W/System.err:     at android.view.ViewRootImpl$InputStage.deliver(ViewRootImpl.java:3859)
W/System.err:     at android.view.ViewRootImpl$InputStage.onDeliverToNext(ViewRootImpl.java:3912)
W/System.err:     at android.view.ViewRootImpl$InputStage.forward(ViewRootImpl.java:3878)
W/System.err:     at android.view.ViewRootImpl$AsyncInputStage.forward(ViewRootImpl.java:4038)
W/System.err:     at android.view.ViewRootImpl$ImeInputStage.onFinishedInputEvent(ViewRootImpl.java:4199)
W/System.err:     at android.view.inputmethod.InputMethodManager$PendingEvent.run(InputMethodManager.java:2400)
W/System.err:     at android.view.inputmethod.InputMethodManager.invokeFinishedInputEventCallback(InputMethodManager.java:1964)
W/System.err:     at android.view.inputmethod.InputMethodManager.finishedInputEvent(InputMethodManager.java:1955)
W/System.err:     at android.view.inputmethod.InputMethodManager$ImeInputEventSender.onInputEventFinished(InputMethodManager.java:2377)
W/System.err:     at android.view.InputEventSender.dispatchInputEventFinished(InputEventSender.java:141)
W/System.err:     at android.os.MessageQueue.nativePollOnce(Native Method)
W/System.err:     at android.os.MessageQueue.next(MessageQueue.java:323)
W/System.err:     at android.os.Looper.loop(Looper.java:136)
W/System.err:     at android.app.ActivityThread.main(ActivityThread.java:6186)
W/System.err:     at java.lang.reflect.Method.invoke(Native Method)
W/System.err:     at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:889)
W/System.err:     at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:779)
```
* Lint complains: Ran lint on variant release: 43 issues found

# Features
* Change: Remove build warnings
* Add: search/filter for passwords
  * Add: highlighting
* Add: password generation
* Add: create a new file
* Maybe: nicer graphics

# Done
* Add: FloatingActionButton
  * Creating new items now possible
* Add: Show icons for every entry in the list view
* Change: Wrong password message
* During "encoding ..." click somewhere
  *  Exception:
  ```
  FATAL EXCEPTION: main
                Process: de.igloffstein.maik.aRevelation, PID: 16079
                java.lang.NullPointerException: Attempt to invoke virtual method 'java.lang.String android.app.Activity.getString(int)' on a null object reference
                    at com.github.marmaladesky.ARevelation$AskPasswordDialog$DecryptTask.onPostExecute(ARevelation.java:386)
                    at com.github.marmaladesky.ARevelation$AskPasswordDialog$DecryptTask.onPostExecute(ARevelation.java:325)
                    at android.os.AsyncTask.finish(AsyncTask.java:667)
                    at android.os.AsyncTask.-wrap1(AsyncTask.java)
                    at android.os.AsyncTask$InternalHandler.handleMessage(AsyncTask.java:684)
                    at android.os.Handler.dispatchMessage(Handler.java:102)
                    at android.os.Looper.loop(Looper.java:154)
                    at android.app.ActivityThread.main(ActivityThread.java:6186)
                    at java.lang.reflect.Method.invoke(Native Method)
                    at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:889)
                    at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:779)
  ```