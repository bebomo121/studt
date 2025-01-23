import React, { useState } from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';
import { Frame } from '@nativescript/core';
import { MainScreen } from './screens/MainScreen';
import { SubjectDetailsScreen } from './screens/SubjectDetailsScreen';
import { AddSubjectScreen } from './screens/AddSubjectScreen';
import { UserSettingsScreen } from './screens/UserSettingsScreen';
import { AppProvider } from './context/AppContext';

const Stack = createStackNavigator();

export function App() {
  return (
    <AppProvider>
      <NavigationContainer>
        <Stack.Navigator
          initialRouteName="Main"
          screenOptions={{
            headerStyle: {
              backgroundColor: '#4F46E5',
            },
            headerTintColor: '#fff',
            headerTitleStyle: {
              fontWeight: 'bold',
            },
            headerTitleAlign: 'center',
          }}
        >
          <Stack.Screen 
            name="Main" 
            component={MainScreen} 
            options={{ title: 'منظم دراستي' }} 
          />
          <Stack.Screen 
            name="SubjectDetails" 
            component={SubjectDetailsScreen} 
            options={{ title: 'تفاصيل المادة' }} 
          />
          <Stack.Screen 
            name="AddSubject" 
            component={AddSubjectScreen} 
            options={{ title: 'إضافة مادة جديدة' }} 
          />
          <Stack.Screen 
            name="UserSettings" 
            component={UserSettingsScreen} 
            options={{ title: 'إعدادات المستخدم' }} 
          />
        </Stack.Navigator>
      </NavigationContainer>
    </AppProvider>
  );
}
