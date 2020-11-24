
#### expo setting

    
    expo init [projectname]
    expo install react-native-webview
    expo install expo-permissions
    expo install expo-ads-admob

            "ios": {
                "supportsTablet": true,
                "bundleIdentifier": "com.zuzulala.appname",
                "buildNumber": "1.0.0"
            },
            "android": {
                "package": "com.zuzulala.appname",
                "versionCode": 1,
                "config": {
                "googleMobileAdsAppId": "ca-app-pub-3940256099942544~3347511713"
                },
                "permissions": ["CAMERA", "READ_EXTERNAL_STORAGE"]
            },
    
+ splash  "backgroundColor": "#51A9AB"



#### expo webview

    
    import * as React from 'react';
    import { WebView } from 'react-native-webview';
    import { StyleSheet, Text, View } from "react-native";
    import {
    AdMobBanner
    } from 'expo-ads-admob';

    export default class App extends React.Component {


    render() {
        return (
        <View style={styles.container}>
            <WebView source={{ uri: 'my uri' }} style={{ marginTop: 20 }} />
            <AdMobBanner
            style={styles.bottomBanner}
            bannerSize="smartBannerPortrait"
            adUnitID="ca-app-pub-3940256099942544/6300978111" // Test ID, Replace with your-admob-unit-id
            />
        </View>
        );
    }
    }
    const styles = StyleSheet.create({
    bottomBanner: {
        position: "absolute",
        bottom: 0
    },
    container: {
        flex: 1,
        backgroundColor: "#fff",
    }
    });
    
    

#### expo command

    
    expo start
    expo build:android
    expo publish
    