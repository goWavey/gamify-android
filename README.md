## Getting started

### Step 1: Add the JitPack repository to your build file
#### Add it in your root build.gradle at the end of repositories:
#### Groovy
```groovy
dependencyResolutionManagement {
  repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
  repositories {
       mavenCentral()
       maven { url 'https://jitpack.io' }
   }
}
```
#### Kotlin DSL
```kotlin
dependencyResolutionManagement {
  repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
  repositories {
       mavenCentral()
       maven { url = uri("https://jitpack.io") }
   }
}
```
### Step 2: Add the dependency 
#### Groovy
```groovy
dependencies {
   implementation 'com.github.goWavey:gamify-android:$currentVersion'
}
```
#### Kotlin DSL
```kotlin
dependencies {
   implementation("com.github.goWavey:gamify-android:$currentVersion")
}
```
### Step 3: Initialize SDK
```kotlin
GoWaveyFactory.initialize(
   appKey = YOUR_APP_KEY,
   memberId = YOUR_MEMBER_ID
)
```
## Usage
#### Update activity
##### Updates activity with callback to check if there is any reward available after update
```kotlin
public fun updateActivity(
        activityInfo: ActivityInfo,
        onLoading: () -> Unit,
        onResult: (rewardStatus: RewardStatus) -> Unit
    )
```
#### Get trophy case
##### Gets user trophy case with result callback
```kotlin
public fun getTrophyCase(
        trophyId: String,
        onLoading: () -> Unit,
        onResult: (trophyCaseStatus: TrophyCaseStatus) -> Unit
    )
```
#### Show badge rewards
##### Presents screen with rewards to user
```kotlin
public fun showBadgeRewards(badges: List<BadgeReward>)
```
#### Show trophy case
##### Presents screen with trophy case to user
```kotlin
public fun showTrophyCase(rewardItems: RewardItems)
```
