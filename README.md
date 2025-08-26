override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)

    // Example: Display a welcome message in a TextView
    val textView = findViewById<TextView>(R.id.textView)
    textView.text = "Welcome! Activity created."
}
override fun onStart() {
    super.onStart()

    // Example: Start a progress bar animation
    val progress = findViewById<ProgressBar>(R.id.progressBar)
    progress.visibility = View.VISIBLE
}
override fun onResume() {
    super.onResume()

    // Example: Start listening to GPS updates
    Log.d("LifecycleDemo", "[onResume] → start location tracking")
    // locationManager.requestLocationUpdates(...)   (pseudo-code)
}
override fun onPause() {
    super.onPause()

    // Example: Pause a running video
    if (videoView.isPlaying) {
        videoView.pause()
    }
}
override fun onStop() {
    super.onStop()

    // Example: Save user progress to SharedPreferences
    val prefs = getSharedPreferences("GameData", MODE_PRIVATE)
    prefs.edit().putInt("level", 5).apply()
}
override fun onDestroy() {
    super.onDestroy()

    // Example: Release a MediaPlayer resource
    mediaPlayer.release()
}
