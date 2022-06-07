# STEP 4 - Gestures and AI

By default the Bangles didn't have an AI model installed - so to start off
the AI working you just need to load one into the on-watch storage.

If you just want to try this out quickly, install the 'Gesture Test' app from the app store. The existing model is not trained on a very wide variety of data and will almost certainly not work for you very well - this should change in the future though!

When you're connected with the Web IDE, copy and paste the following:

```
require("Storage").write(".tfmodel",atob("HAAAAFRGTDMAABIAHAAEAAgADAAQABQAAAAYABIAAAADAAAAjA0AABAEAAD4AwAAPAAAAAQAAAABAAAADAAAAAgADAAEAAgACAAAAAgAAAAMAAAAEwAAAG1pbl9ydW50aW1lX3ZlcnNpb24ADQAAALADAACIAwAAWAMAAKQBAABcAQAAVAEAAEwBAABEAQAAEAEAAAgBAAAAAQAAHAAAAAQAAACu/P//BAAAAAUAAAAxLjUuMAAAAML8//8EAAAA0gAAAMJbJV3AgRwc/Nn1I0Qd5WDwPa0nY6nMbPyvfyOWOlqqf+64Juoa5kjpQVjoHTubf/NpJEH1Sqe0/PfJ5/o08zInA5f6fyg/vRaJEX9VQE5BPlRI0EP1Imq8NkNBLz3Q1hW5k9frf1Lfuc/rEwfGJqbG/txEf35Ey0jgICJ/B+vyu1FF8M+HA2ZcLhAX+QGB26MS3iLLDxnLNlvp9jbo8gM/5YEc0RoWA+W+Ih9T3AyBSNRX4Ew+739Y9R3p+cnS/dj283/BrQDWUu/y4Q8JAwj+5QAA4Pz//+T8//+q/f//BAAAACQAAABejWTlyU3qNn6j53/W2AR0lmjJ9d87YN1cNbBDobHjz5gdMFIY/f//HP3//yD9///m/f//BAAAADgAAADB////e////zwAAACt////5P////3///8yAAAAmP///53///9K////SP///2H///+J////c////yr+//8EAAAApAEAAA4mHQIO1TUu59UbG4FFDeDwNN3sEtUHD18IISYb5aXfCQ0g6/wWDMADFirm8M7t9f4H1eMQluL9Btze72b+5wXX08vbHvLxET4L+xHtFeHZ5NfHV/zUByIHzTf/rxUS28LqwaXnhn8izicXm7z7t+Ja6dHaVL8zE6oR6TwY3LUxFktGE/DcDQz71rkc9SrmL+zs6+3/yTse/xvcHcsIgenD5OHuJeT199TsxRCi6bVGzgb579Xj2vTt2g/RqTAbAsroB9oAtgbn7AkS8fEJ0O8x/nML+1Xf/cAqK8Yo9yvVIjztKSQT+NH09AdCIb/6Af/VD9+EI+vvKuvEEk9h5k8PtNrNIucw/xGBFVzOCQ3q/wH+BBtoCOf74smpLzb37xcvFlcQEPAMmP4o9+L5JU8QMgHG5wrINjRx8/UnPBc57cvo79oGAUzs5jTzFWznEvzP6s8Wf+gQHOn2QAYD/hE8Fuw45P8B0y0GCgr4AyrsAgjRH0XpGRM0+gD9YPoB++3wM/TcDn+fDf1lAAoaCtP4M/3kbQvrATrd6g/y7/rv6Kwj3Nr///8EAAAAGAAAAAYBAADiAQAA2P///5f+//+6////Mf///wAABgAIAAQABgAAAAQAAAAYAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAaP///w8AAABUT0NPIENvbnZlcnRlZC4AAQAAAAQAAAD09v//3AEAANABAADEAQAABAAAAAYAAACYAQAAQAEAANgAAACEAAAAOAAAAAQAAACK/v//BAAAABAAAAAEAAAAAQAAAAwAAAABAAAAAAAAAAAADgAYAAgADAAQAAcAFAAOAAAAAAAACAEAAAAcAAAAEAAAAAgAAAAEAAQABAAAAAEAAAAAAAAAAwAAAAoAAAAJAAAAAQAAAAAADgAaAAgADAAQAAcAFAAOAAAAAAAABQIAAAA8AAAAMAAAABQAAAAAAA4AGAAHAAgADAAQABQADgAAAAAAAAEBAAAALgAAAAEAAAAuAAAAAQAAAAoAAAABAAAACAAAAKr///8AAAABPAAAADAAAAAUAAAAEAAYAAAACAAMAAcAEAAUABAAAAAAAAABAQAAAAEAAAACAAAAAgAAAAEAAAAIAAAAAwAAAAUAAAAGAAAABwAAAAAADgAUAAAACAAMAAcAEAAOAAAAAAAAATAAAAAkAAAAEAAAAAwAEAAGAAgADAAHAAwAAAAAAAEBAQAAAAEAAAABAAAABQAAAAMAAAACAAAAAwAAAAQAAAAAAAoAEAAEAAgADAAKAAAAAwAAABAAAAAEAAAAAQAAAAIAAAABAAAACwAAAAEAAAAMAAAAAQAAAAsAAAANAAAAEAcAAJwGAAAcBgAAAAUAAPwDAAB4AwAAvAIAABgCAACMAQAACAEAAHQAAAA8AAAABAAAANj///8YAAAABAAAAAgAAABJZGVudGl0eQAAAAACAAAAAQAAAAYAAAAMAAwABAAAAAAACAAMAAAAHAAAAAQAAAAMAAAAYWNjZWxlcmF0aW9uAAAAAAQAAAABAAAAMgAAAAEAAAADAAAAmvn//wAAAAl0AAAABgAAAEQAAAAEAAAAjPn//zAAAAAkAAAAGAAAAAQAAAABAAAAgP////////8AAAAAAQAAAN6l9z4BAAAAOK72QgEAAAAAAAAAIAAAAHNlcXVlbnRpYWwvbWF4X3Bvb2xpbmcyZC9NYXhQb29sAAAAAAQAAAABAAAAAQAAAAEAAAAGAAAAKvr//wAAAAlsAAAACAAAACwAAAAEAAAAjPr//xgAAAAEAAAAAQAAAAAAAAAAAAAAAAAAAAEAAABVoaw7MAAAAHNlcXVlbnRpYWwvZGVuc2UvTWF0TXVsL1JlYWRWYXJpYWJsZU9wL3RyYW5zcG9zZQAAAAACAAAABgAAAAYAAACq+v//AAAACWwAAAAJAAAARAAAAAQAAACc+v//MAAAACQAAAAYAAAABAAAAAEAAACA/////////wAAAAABAAAA3qX3PgEAAAA4rvZCAQAAAAAAAAAYAAAAc2VxdWVudGlhbC9jb252MmRfMS9SZWx1AAAAAAQAAAABAAAALgAAAAEAAAAGAAAAMvv//wAAAAKQAAAAAgAAAGQAAAAEAAAAlPv//zwAAAAEAAAABgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAYAAABUbvA6FaemOke74Do4TZA6gTLYOpTt+zofAAAAc2VxdWVudGlhbC9jb252MmRfMS9Db252MkRfYmlhcwABAAAABgAAANL7//8AAAAJnAAAAAMAAABkAAAABAAAADT8//88AAAABAAAAAYAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAGAAAAQ3uTO3hzTDv12Yk71QcxO86dhDuqiJo7KQAAAHNlcXVlbnRpYWwvY29udjJkXzEvQ29udjJEL1JlYWRWYXJpYWJsZU9wAAAABAAAAAYAAAAFAAAAAQAAAA4AAACK/P//AAAACWQAAAAHAAAAQAAAAAQAAAB8/P//LAAAACAAAAAUAAAABAAAAAEAAACA/////////wEAAADfq9A+AQAAADPbz0IBAAAAAAAAABYAAABzZXF1ZW50aWFsL2NvbnYyZC9SZWx1AAAEAAAAAQAAAC4AAAABAAAADgAAAAr9//8AAAAC8AAAAAQAAADEAAAABAAAAGz9//98AAAABAAAAA4AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAADgAAAIieCjtEoPM6zIP5OgV3xjosFgQ7+qsTOwl55zpbKvM6YZ8XO+0qyjoJ/CM7Eq0SO2aMIDuFGvM6HQAAAHNlcXVlbnRpYWwvY29udjJkL0NvbnYyRF9iaWFzAAAAAQAAAA4AAAAK/v//AAAACfwAAAALAAAAyAAAAAQAAABs/v//gAAAAAQAAAAOAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAOAAAAqzQ2O3QdIDs6/CM7Nm8CO3aeLTvLGkI7syAYO/bPHzs3TEc7Md4EO/GLVzu9y0A7uAdTO43FHzsnAAAAc2VxdWVudGlhbC9jb252MmQvQ29udjJEL1JlYWRWYXJpYWJsZU9wAAQAAAAOAAAABQAAAAEAAAADAAAAIv///wAAAAlgAAAACgAAAEAAAAAEAAAAFP///ywAAAAgAAAAFAAAAAQAAAABAAAABwAAAAAAAAABAAAAw8JCPwEAAAAAALZCAQAAAAAAzsIRAAAAYWNjZWxlcmF0aW9uX2ludDgAAAAEAAAAAQAAADIAAAABAAAAAwAAAJ7///8AAAACUAAAAAEAAAA0AAAAEAAAAAwADAAAAAAABAAIAAwAAAAUAAAABAAAAAEAAAAAAAAAAAAAAAEAAACD/yY7DQAAAElkZW50aXR5X2JpYXMAAAABAAAABgAAAAAADgAYAAgABwAMABAAFAAOAAAAAAAACWgAAAAFAAAATAAAABAAAAAMABQABAAIAAwAEAAMAAAALAAAACAAAAAUAAAABAAAAAEAAAAJAAAAAAAAAAEAAACacSU/AQAAALcXmUIBAAAAmoCwwg0AAABJZGVudGl0eV9pbnQ4AAAAAgAAAAEAAAAGAAAABQAAAGAAAABEAAAAKAAAABwAAAAEAAAA1v///wAAAAYCAAAAAAAGAAgABwAGAAAAAAAAcvL///8AAAARAgAAAAAACgAOAAcAAAAIAAoAAAAAAAAJBAAAAAAACgAMAAcAAAAIAAoAAAAAAAADAwAAAA=="));
require("Storage").write(".tfnames","swipeleft,swiperight,upup,waggle,clap2");
```

Now, the AI should be enabled. If you upload the code below, the watch should then
print what it believes your gesture is - one of `swipeleft`, `swiperight`,
`upup`, `waggle`, `clap2` - as well as the raw output vector from Tensorflow.

```
Bangle.on('aiGesture',(gesture,raw)=>print(gesture,raw));
```

The following code would output the gesture on the watches screen, so you
can see it even without an active BLE connection.

```
Bangle.on('aiGesture',(gesture)=>{
  E.showMessage(gesture);
  setTimeout(()=>g.clear(), 2000);
});
```

If you're using [the Tensorflow Gesture Colab](https://colab.research.google.com/) (full info on https://nodewatch.dev/software)
all you need to do to run your model is get the base64 encoded data it produces, stick it inside:

```
require("Storage").write(".tfmodel",atob("..."))
```

and paste it into the left-hand side of the IDE.

The `.tfnames` file maps the vector output of Tensorflow to human-readable names - so you'll need to modify it only if you plan on adding new gesture names.

## Getting more data!

If you need more data to train your tensorflow model, log in via the Web IDE
then upload the following code:

```
// ******* Gesture collecting code ********
name="Gesture";
event_acc="left_acc"; //file name for acclerometer data
event_mag="left_mag"; //file name for magnetometer data


var fname = 1;

function gotGesture(d) {
  
  var f = require("Storage").open(event_acc + "." + fname + ".csv", "a");
  var g = require("Storage").open(event_mag + "." + fname + ".csv", "a");

  print("timestamp, x, y, z");
  //print(d);
  
  f.write("timestamp, x, y, z\n");
  g.write("timestamp, mx, my, mz, mdx, mdy, mdz\n");
  
  for (var j=0;j<d.length;j+=3) {
    print(j +", ", d[j] + ", " + d[j+1] + ", " + d[j+2] );
    f.write(j + ", " + d[j] + ", " + d[j+1] + ", " + d[j+2] +"\n" );
    c= Bangle.getCompass(); //c for compass
    g.write(j +"," + c.x +"," + c.y +"," + c.z +"," + c.dx +"," + c.dy +"," + c.dz);}
  print("timestamp, mx, my, mz, mdx, mdy, mdz");
  print(j +"," + c.x +"," + c.y +"," + c.z +"," + c.dx +"," + c.dy +"," + c.dz);

  //if you want your display to have the graph of acceleration uncomment the following part
  /*g.clear();
  g.setColor(1,1,1);
  var my = g.getHeight()/2;
  var sy = my/128;
  var sx = g.getWidth()/(50*3);
  g.drawLine(0,my,g.getWidth(),my);
  for (var i=0;i<d.length-3;i+=3) {
    for (var c=0;c<3;c++) {
      g.setColor(c==0,c==1,c==2);
      g.drawLine(i*sx, my+d[i+c]*sy, (i+3)*sx, my+d[i+c+3]*sy);
    }
  }
  g.flip(1);
  */
}
Bangle.setCompassPower(1);
Bangle.on('gesture',gotGesture);
```

Run `name="MyGesture"` then repeat the gesture over and over. Each time
a line of data will be output to the Web IDE console and the display
will show a graph of the acceleration.

You can then copy/paste that that data and use it in the Google Colab.
