<template>
  <app-navigator>
  </app-navigator>
</template>

<script>
import {
  createAppContainer,
  createStackNavigator
} from "vue-native-router";
import HomeScreen from "./screens/HomeScreen.vue";
import DichScreen from "./screens/DichScreen.vue";
import DetailsScreen from "./screens/DetailsScreen.vue";
import NewsScreen from "./screens/NewsScreen.vue";
import FlexScreen from "./screens/FlexScreen.vue";
import SLotScreen from "./screens/SLotScreen.vue";
import NewsLoadmoreScreen from "./screens/NewsLoadmoreScreen.vue";
console.disableYellowBox = true;
const StackNavigator = createStackNavigator(
  {
    Home: HomeScreen,
    Details: DetailsScreen,
    Dich:DichScreen,
    News:NewsScreen,
    Flex:FlexScreen,
    Slot:SLotScreen,
    Loadmore:NewsLoadmoreScreen
  },
  {
    initialRouteName: 'Home'
  }
);
const AppNavigator = createAppContainer(StackNavigator);
export default {
  components: { AppNavigator }
}
</script>