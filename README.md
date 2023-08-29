<h1>Daily Updates</h1>

<hr>
<h2>29 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>
  KidsCare App
  <ul>
    <li>created a filp Card option with Annimation in which fron face is image and back face is text</li>
  </ul>
    <ul>
    <li>created a kidCard</li>
      <ul>
    <li>Created a new kid card adding option with name, dob, weight, height, boy or girl button with one selection in a bottomsheet</li>
        <li>get that data into viewmodel</li>
        <li>implemented a database</li>
        <li>In database added details of kid</li>
        <li>upsert all the details of kid</li>
        <li>get all the detailsof kid to show on home Screen</li>
        <li>add options to change the color in every card</li>
  </ul>
  </ul>
  </li>
</ol>
<hr>
<h2>28 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>
  KidsCare App
  <ul>
    <li>created a new base app for kids Care and clone it to github</li>
    <li>Created and implemented necessary files such as viewmodel, services and navigaitons</li>
    <li>Added images and icons to the resource liabrary</li>
    <li>Created a navigation in which selected item is highlighted</li>
    <li>Created a profile option of images and column of necessary options</li>
  </ul>
  </li>
</ol>
<hr>
<h2>25 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>
    Fido2 app
    <ul>
      <li>Freshly build the new fido2 App</li>
      <li>implemented base api url of codelab : not worked</li>
      <li>created a new api url from glitch.me : "https://glitch.com/edit/#!/rift-cheerful-thistle?path=.env%3A1%3A0"</li>
      <li>new url woked but needed sha key, Created a sha key to implement in website : sha key created by signingReport</li>
      <li>product uploaded to github</li>
    </ul>
  </li>
  <li>
    learn About permissions : "https://developer.android.com/training/permissions/requesting-special"
    <ul>
      <li>Requesting runtime permission and Special Permissions</li>
      <li>managing Runtime Permissions</li>
    </ul>
  </li>
</ol>
<hr>
<h2>24 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>
    CameraX functionalities
    <ul>
      <li>CameraX is a Jetpack library by Google that adds camera functionality to Android apps consistently across devices and versions.</li>
      <li>It provides features like camera preview, photo capture, video recording, tap-to-focus, and pinch-to-zoom with a few lines of code.</li>
      <li>It provides features like camera preview, photo capture, video recording, tap-to-focus, and pinch-to-zoom with a few lines of code.</li>
      <li>The preview use case streams images from the camera sensor to the UI, important for framing shots or video calls.</li>
      <li>Image capture captures high-quality photos, video capture handles recording and mixing audio and video, and image analysis allows for image processing and machine learning inference, including ML Kit integration.</li>
    </ul>
  </li>
  <li>
    Fido2 application
    <ul>
      <li>
        build the Application
        <ul>
          <li>Application needed updaetes to the recent versions of kotlin</li>
          <li>when i updated it buld dupplicated Apllication and have kapt3 error</li>
        </ul>
      </li>
      <li>
        re-build the Application
        <ul>
          <li>freshly import the Apllication</li>
          <li>only updated kotlin version not full App</li>
          <li>it ran but Showing error : "The incoming request cannot be validated"</li>
        </ul>
      </li>
    </ul>
  </li>
  
</ol>
<hr>
<h2>23 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>
    Created qr Code generator app:
    <ul>
      <li>get the api link to generate qr : https://api.qrserver.com/v1/create-qr-code/?size=550x550&data=</li>
      <li>
        created a text box to insert a value link in api to generate the qr and async it with asynImage
        async Image implementation("io.coil-kt:coil-compose:2.4.0")
      </li>
      <li>
        make All the qr Downloadable by getting permissions of read storage,write Storage &Download mananger in manifest xml
        <ol>
          <li>'uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"
        android:maxSdkVersion="28" '</li>
            <li>'uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"'</li>
            <li>'uses-permission android:name="android.permission.ACCESS_DOWNLOAD_MANAGER" '</li>
        </ol>
      </li>
      <li>
        Coded a downloading function to Download qr from the link to a given coontext
        <ul>
          <li>
            "fun downloading(imageLink:String, title:String, context: Context ){
                val request = DownloadManager.Request(Uri.parse(imageLink))
                request.setAllowedNetworkTypes(DownloadManager.Request.NETWORK_WIFI or                           DownloadManager.Request.NETWORK_MOBILE)
                request.setTitle("Download")
                request.setDescription("Downloading Image")
                request.setNotificationVisibility(DownloadManager.Request.VISIBILITY_VISIBLE_NOTIFY_COMPLETED)
                request.setDestinationInExternalPublicDir(
                    Environment.DIRECTORY_DOWNLOADS,
                    "${System.currentTimeMillis()}")            
                val manager = context.getSystemService(Context.DOWNLOAD_SERVICE) as DownloadManager
                manager.enqueue(request)
            }"
          </li>
        </ul>
      </li>
      <li>
        created a navigation page to navigate though main Screen to scan or Create Screen
      </li>
    </ul>
  </li>
  <li>
    learn About Camerax Liabrary :
     <ul>
          <li>
            implementation of camera Liabrary:
            <ul>
              <li>
                 camera : implementation "androidx.camera:camera-camera2:1.2.3"
              </li>
              <li>
                lifecycle : implementation "androidx.camera:camera-lifecycle:1.2.3"
              </li>
              <li>
                Android view - implementation "androidx.camera:camera-view:1.2.3"
              </li>
              <li>
                Camera extension for different actions :implementation "androidx.camera:camera-extensions:1.2.3"
              </li>
              <li>
                Accompanist : implementation "com.google.accompanist:accompanist-permissions:0.31.2-alpha"
              </li>
            </ul>
          </li>
        </ul>
    </li>
    <li>
      give permissions to camera app in mannifest:
      uses-feature
        android:name="android.hardware.camera"
        android:required="false"
      uses-permission android:name="android.permission.CAMERA"
    </li>
    <li>
      Preview camera in android view to get the view of camera
    </li>
</ol>
<hr>
<h2>22 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>Succesfuly fetched data from api to view model to print on screen</li>
  <li>Learn about roomDB to get and store information on local db</li>
  <li>Created a small projct to insert and delete data from Local db</li>
</ol>
<hr>
<h2>21 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>just tried to get api data to store in view model to print in screen</li>
</ol>
<hr>
<h2>18 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>Learn About a retrofit get to get the data from api</li>
  <li>Created a project to get the data from api </li>
</ol>
<hr>
<h2>17 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>Research Why Kotlin is better than flutter and react native</li>
</ol>
<hr>
<h2>16 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>give basic changes to the chat app sush as color, images, text</li>
  <li>learn about the Coroutines </li>
  <li>Created a small project on Coroutine </li>
</ol>
<hr>
<h2>14 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>created a new Chat option with chat and group tab</li>
  <li>Coded a click to send message in chat window</li>
  <li>Created a chat grop window</li>
</ol>
<hr>
<h2>11 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>Code a Chat page screen add recent chat and groups tabs and make search button which on click shows search bar and hide it</li>
  <li>add floating button on the app to add new chat options from contacts and add Searching list so that it can search contacts from the search bar </li>
  <li>code new chat page which will get to the new contacts </li>
</ol>
<hr>
<h2>10 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>learn About the navigation of an appliction..how apps navigate from one page to another and share data and functionalities</li>
  <li>again coded the planters app from scratch with implementing view model and navigation format  </li>
  <li>Add Navigation functionalities to the app to go on the Chat page from BottomSheet</li>
</ol>
<hr>
<h2>9 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>give funtion to more options and coded the bottom sheet scaffold layout</li>
  <li>learn about the architecture and view model of an android application </li>
  <li>build a counter app by implementin view model architecture</li>
</ol>
<hr>
<h2>8 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>Rectified Add planters menu in Android app</li>
  <li>Build a bottom sheet for more options in the Planters Bottom Navigation bar </li>
  <li>corrected the layout of the bottom bar , bottom sheet and main page</li>
</ol>
<hr>
<h2>7 August, 2023</h2>
<p>Today's Work</p>
<ol>
  <li>Put UI assets such as images, icons and themes to the planters dashboard app</li>
  <li>build add planters colums in planters Android app to Add planters to their dashboard</li>
  <li>created a class and obects to pass value such as name and icons to planters Android app bottom navigation bar</li>
</ol>

<hr>
<h2>4 August, 2023</h2>
<p>today's work</p>
<ol>
  <li>The MainActivity sets up the app's theme and displays the bottomBar composable as the main content.</li>
  <li>The bottomBar function sets up a bottom navigation bar using the Scaffold and NavigationBar components. It also calls the PlantersDashbord composable as the main content within the scaffold.</li>
  <li>The PlantersDashbord composable is the main content section of the app. It displays user information, buttons, and other content in a Column layout.</li>
  <li>The Info composable displays the user's profile picture, a greeting, and buttons for tagged, unminted, and minted trees.</li>
  <li>The FrameButtons composable is used to create custom buttons with a circular profile picture and a label, displaying the number of tagged, unminted, and minted trees.</li>
  <li>The mapScroll and PlanterScroll composable functions are placeholders for displaying maps and planters, respectively.</li>
</ol>
