# Android-FFmpegExecuter
simple ffmpeg command executer for android

Something wrong on this project....sample application module is bigger than library module. i will split app modul.

## Example
```java
mExecuter = new FFmpegExecuter(getApplicationContext());
```

if you want to know ffmpeg log while process running, set this listener 
```java
mExecuter.setOnReadProcessLineListener(new FFmpegExecuter.OnReadProcessLineListener() {
    @Override
    public void onReadProcessLine(String line) {
        // TODO something
    }
});
```

you must call init() before put command
put some commands
```java
mExecuter.init();
mExecuter.putCommand("-y");
mExecuter.putCommand("-i");
mExecuter.putCommand(originalPath);
mExecuter.putCommand("-vcodec");
mExecuter.putCommand("libx264");
mExecuter.putCommand("-profile:v");
mExecuter.putCommand("baseline");
mExecuter.putCommand("-level");
mExecuter.putCommand("3.1");
mExecuter.putCommand("-b:v");
mExecuter.putCommand("1000k");
mExecuter.putCommand("-vf");
mExecuter.putCommand(filter);
mExecuter.putCommand("-c:a");
mExecuter.putCommand("copy");
mExecuter.putCommand(Environment.getExternalStorageDirectory().getAbsolutePath() + "/result.mp4");
```

and execute command
```java
mExecuter.executeCommand();
```

## Licence
Copyright 2015 Mabi

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this work except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.