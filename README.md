# LivePhotoGenerator.swift
A Swift library for creating and saving Live Photos

#### Creating and Saving a Live Photo:
```swift
// Create a LivePhoto object with a image path and video path
LivePhotoGenerator.create(inputImagePath: imagePath, inputVideoPath: videoPath) { (livePhoto: LivePhoto?, error: Error?) in

    // Unwrap object
    if let livePhoto = livePhoto {

        // Set the Live Photo in a PHLivePhotoView
        let livePhotoView = PHLivePhotoView(frame: rect)
        livePhotoView.livePhoto = livePhoto

        // Save Live Photo to Photo Library
        livePhoto.writeToPhotoLibrary(completion: { (livePhoto: LivePhoto, error: Error?) in

          if error == nil {
            ...
          }
        })
    }
}
```

#### Extra Tool (LivePhoto Method):
```swift
// Move paired image and video to new path
livePhoto.movePairedFilesTo(path: path, completion: { (success: Bool, error: Error?) in

    if success {
        ...
    }
})
```

## Live Photo Generator Demo
The "Demo" is a basic reference application created to show how to develop applications using the Live Photo Generator library.

### Installation
To access the project, run the following:
```
git clone --recursive https://github.com/OlegAba/LivePhotoGenerator.git
```
Open ```Demo.xcodeproj``` in the Demo folder
