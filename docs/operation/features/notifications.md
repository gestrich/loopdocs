## Loop Notifications

Loop provides discrete notifications on the iPhone and Watch which will appear on the (locked) screen and vibrate, depending on your notification settings of Loop.

## Loop App Expiration Notification

Profile expiration notification was added with Loop 2.2.5.

![Notification display when near the Loop App expiration date](img/loop-app-expiration-warning.png){width="250"}
{align="center"}

* When fewer than 20 days remain until profile expiration, you'll get a notification when you open the app but no more frequently than every 2 days
* When fewer than 24 hours remain, you'll get a notification when you open the app, once every hour at most
* Simply tap on the `More Info` button of the notification to go directly to the [LoopDocs Updating](../../build/updating.md) page.

### Free (7-day) Loop App Expiration Notification

The expiration notification pattern is the same as for the Paid Loop App. You may want to add an [Expiration Notification Customization](../../build/code_customization.md#expiration-notification-customization) to modify the first appearance and frequency of the notification.


## Loop App Expiration Date

!!! tip "Coming Soon"
    Available in dev now; will be in the next release:

    * A new **App Profile** section was added to the bottom of the Loop Settings screen
    * Valid for Mac-Xcode builds
        * Profile Expiration count-down in days, as well as expiration date and time
        * Direct link to the LoopDocs How to Update page

#### For Loop 2.2.5 through Loop 3.0

If you want to see the expiration date at any time:

* Loop 2.2.5 through 2.2.9: tap on Settings, then tap on Issue Report
* Loop 3.0.0: tap on Settings, scroll down and tap on Support, then tap on Issue Report

The expiration date is near the top of the report (to the right of `profileExpiration`).  If you don't see that, time to rebuild to get that feature. Once you've viewed the expiration date, tap Settings to back out of the Issue Report display. The time is in GMT, so adjust to your own time zone if you procrastinated until the last minute.

![Issue report displays Loop App expiration date](img/loop-app-expiration-issue-report.jpeg){width="250"}
{align="center"}

## Omnipod Beeps

Most pod beep alarms are disabled for a more discrete use of pods than is available with the PDM. Only the following audible acknowledgments or alarms are used. Some can be configured in [Omnipod: Notification Settings](../../loop-3/omnipod.md#notification-settings):

- Pod activated acknowledgment when filling the pod with enough insulin when pairing a new Pod.
- Pod expiration advisory alarm, which you can configure between 48 and 72 hours (3 days)
- Pod low reservoir alert
    * Note that the pod may continue delivering after the reservoir reports 0 U
    * The pod will continue until the pod runs out of insulin or 4 U is delivered, which ever comes first
    * Loop will update the actual delivery amounts based on pod reported information
- Pod deactivation acknowledgment
- Pod fault alarm (also called a screamer) when reaching the max life of the Pod: 80 hours (3 days + 8 hours), running out of insulin or a fault/occlusion happens
    * Screamers are silenced using the [Replace Pod](../../loop-3/omnipod.md#replace-pod) row on the pod settings page
    * The one exception is if communications with the pod is lost and cannot be restored - in that case, you will be offered the chance to discard the pod from Loop but will still want to [Silence the Pod](../../faqs/omnipod-faqs.md#what-do-you-do-to-stop-a-screaming-pod)

## Notification settings for Loop

You can customize the way notifications of Loop are behaving in the Settings App of the iPhone:

![img/iphone-settings-notifications.png](img/iphone-settings-notifications.png){width="250"}
{align="center"}

Loop 3 Notifications Settings:

![Loop 3 iPhone Notifications Settings](img/iphone-notifications-loop3.jpeg){width="250"}
{align="center"}

Mark **Loop 3** notifications as **time-sensitive** and ask for **immediate delivery**:

- tick the **`Immediate Delivery`** so that notifications are delivered right away
- enable the **`TimeSensistive Notifications`** checkbox 

!!! info  "Notification Delivery"

    You will see the `Notification Delivery` section only if you previously toggled on `Settings / Notifications / Scheduled Summary` in order to receive a summary of notifications at a certain time of the day. If this is not what you want, simply ignore it.

!!! info  "Announce Notifications"

    The `Announce Notifications` section is displayed only if you previously turned on the toggle `Settings / Notifications / Announce Notifications`. Use it if you want Siri to read Loop's notifications out loud on CarPlay, and AirPods...

Make sure **Loop notifications** are **allowed** in your **Focus mode**.
Edit the focus mode to:

- add `Loop` to the list of apps with allowed notifications
- enable the `Time Sensitive Notifications` toggle button

## Loop Failure

At 20, 40, 60, and 120 minutes, there is a Loop Failure notification.
This mostly happens when the connection is lost for a longer period of time between the CGM or the Rileylink and Loop.

![img/loop-failure.png](img/loop-failure.png){width="250"}
{align="center"}

## Bolus Failure

If Loop detects that a bolus was not able to be delivered, it will provide a notification.  Bolus failures are usually due to stale pump data.  Try fetching recent history from the RileyLink menu to update pump data.  Loop will also notify of partial bolus deliveries.

![img/loop-bolus-failure.png](img/loop-bolus-failure.png){width="250"}
{align="center"}

## Low Reservoir

<font color ="orange">**Medtronic**</font>  
At 20% and 10% remaining reservoir volume, there is a Low Reservoir notification.

<font color ="orange">**Omnipod**</font>  
Select your desired notification level for low reservoir
[Omnipod: Notification Settings](../../loop-3/omnipod.md#notification-settings) 

![img/pod-reservoir-10U.png](img/pod-reservoir-10U.png){width="250"}
{align="center"}

## Empty Reservoir

* Loop 2 will notify when the reservoir is empty.

![img/loop-reservoir-empty.png](img/loop-reservoir-empty.png){width="250"}
{align="center"}

* Loop 3 reports No Insulin on the [Heads-Up-Display](../../loop-3/displays_v3.md#pump-status-icon).

![pump alert - red exclamation point with phrase no insulin](../../loop-3/img/loop-3-pump-alert-no-insulin.svg){width="125"}
{align="center"}

<font color ="orange">**Omnipod**</font>
After the reservoir reports 0 U, the pod attempts to deliver insulin when requested.

* After 4 U are delivered, the pod alarms and must be changed
* If during the attempt to deliver the 4 U (below zero), the pod runs out of insulin, the pod alarms and must be changed
* In both cases, the pod reports it is out-of-insulin

## Low Battery (Medtronic)

Loop will notify when battery levels have approximately 8-10 hours of battery life remaining.

## Remote Notifications

Loop does not have a remote notification to other devices.  If you are a remotely monitoring parent, you will want to read [here](https://nightscout.github.io/nightscout/setup_variables/#pushover) about setting up pushover alerts using your Nightscout site if you want proactive notifications of looping related information.

## Loop Follow

Many people use additional apps to assist in following a loved one or to support a loved one who needs help waking up to alarms. One of the more popular options is Loop Follow, written by a parent of a Looper. There are a number of features to assist in remote monitoring with a variety of options for the source of data.

![loop follow graphic from the README page](img/loop-follow.png)

For more information, please read the [Loop Follow](https://github.com/jonfawcett/LoopFollow#loop-follow) documentation. You can build Loop Follow using the same [Build Select Script](../../build/step14.md#build-select-script) you used to build the Loop app. (It's one of the options in the menu.)

Please note that Jon Fawcett makes a clear distinction between his DIY (free) support and his business, Custom Type One. However, both are supported with the same Facebook group, [CustomTypeOne Support (Loop Follow, SugarPixel, Loop Patches)](https://www.facebook.com/groups/loopfollow/).
