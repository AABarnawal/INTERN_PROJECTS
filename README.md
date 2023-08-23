<h1>Daily Updates</h1>

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
      <span>
           val context = LocalContext.current
    val lifecycleOwner: LifecycleOwner = LocalLifecycleOwner.current
    val cameraController: LifecycleCameraController = remember { LifecycleCameraController(context) }
    Scaffold(
        modifier = Modifier.fillMaxSize(),
        floatingActionButton = {
            Button(
                onClick = {
                    val mainExecutor: Executor = ContextCompat.getMainExecutor(context)
                    cameraController.takePicture(mainExecutor, object : ImageCapture.OnImageCapturedCallback() {
                        override fun onCaptureSuccess(image: ImageProxy) {
                            // Process the captured image here
                        }
                    })
                }){ Text(text = "Click")}
        }
    ) { innerPadding: PaddingValues ->
        // Here we will place our content
        AndroidView(
            modifier = Modifier
                .fillMaxSize()
                .padding(innerPadding),
            factory = { context ->
                // TODO: Create our View
                PreviewView(context).apply {
                    setBackgroundColor(Color.White.toArgb())
                    layoutParams = LinearLayout.LayoutParams(100,200)
                    scaleType = PreviewView.ScaleType.FILL_START
                    implementationMode = PreviewView.ImplementationMode.COMPATIBLE
                }.also { previewView ->
                    previewView.controller = cameraController
                    cameraController.bindToLifecycle(lifecycleOwner)
                }
            },
            onRelease = {
                cameraController.unbind()
            }
        )
    }
}
      </span>
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
