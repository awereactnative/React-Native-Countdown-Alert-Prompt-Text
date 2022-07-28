# React-Native-Countdown-Alert-Prompt-Text

# Introduction

This is an example of React Native Countdown Timer using react-native-countdown-component. A CountDown Timer is the reverse of the timer we usually see.  To make a CountDown Timer we will use CountDown component from react-native-countdown-component. Countdown Timer can be used if you are making an App which has some time constraints like if you are making a quiz App, You need some sort of timer to show the remaining time. Let’s see the example below.

# Demo

![hero_image](https://user-images.githubusercontent.com/86215353/181410571-408b77db-1dd4-42b4-a00b-a2451b675866.gif)


# Installation
```

npm install react-native-countdown-component --save

```

# Example
```js

// React Native CountDown Timer | react-native-countdown-component
// https://aboutreact.com/react-native-countdown-timer/

// import React in our code
import React, { useState, useEffect } from 'react';

// import all the components we are going to use
import { SafeAreaView, StyleSheet, Text, View } from 'react-native';

//import CountDown to show the timer
import CountDown from 'react-native-countdown-component';

//import moment to help you play with date and time
import moment from 'moment';

const App = () => {
  const [totalDuration, setTotalDuration] = useState(0);

  useEffect(() => {
    //We are showing the coundown timer for a given expiry date-time
    //If you are making a quize type app then you need to make a simple timer
    //which can be done by using the simple like given below
    //that.setState({ totalDuration: 30 }); //which is 30 sec
    var date = moment().utcOffset('+05:30').format('YYYY-MM-DD hh:mm:ss');
    //Getting the current date-time with required formate and UTC
    var expirydate = '2022-07-20 08:18:10'; //You can set your own date-time
    //Let suppose we have to show the countdown for above date-time
    var diffr = moment.duration(moment(expirydate).diff(moment(date)));
    //difference of the expiry date-time given and current date-time
    var hours = parseInt(diffr.asHours());
    var minutes = parseInt(diffr.minutes());
    var seconds = parseInt(diffr.seconds());
    var d = hours * 60 * 60 + minutes * 60 + seconds;
    //converting in seconds
    setTotalDuration(d);
    //Settign up the duration of countdown in seconds to re-render
  }, []);

  return (
    <SafeAreaView style={styles.container}>
      <View style={styles.container}>
        <Text style={styles.title}>
          React Native CountDown Timer | react-native-countdown-component
        </Text>
        <CountDown
          until={totalDuration}
          //duration of countdown in seconds
          timetoShow={('H', 'M', 'S')}
          //formate to show
          onFinish={() => alert('finished')}
          //on Finish call
          onPress={() => alert('hello')}
          //on Press call
          size={20}
        />
      </View>
    </SafeAreaView>
  );
};

export default App;

const styles = StyleSheet.create({
  container: {
    flex: 1,
    padding: 10,
    justifyContent: 'center',
    alignItems: 'center',
  },
  title: {
    textAlign: 'center',
    fontSize: 20,
    fontWeight: 'bold',
    padding: 20,
  },
});

```

# Tutorial

Coming Soon...
