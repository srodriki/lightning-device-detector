# lightning-device-detector

This is a simple Lightning Component capable of detecting the device the main component is running in and which content has to be shown. Useful if you want to leverage both mobile and desktop components without having to rewrite them to be truthfully adaptive and responsive.

## The Base Component

The core of this repo is a small component called `deviceDetector` with three main abilities:

1. Detects if the component is running on a mobile device or desktop application.
2. Provides you with a couple of two attributes so you can pass in content to be rendered only on one platform. You can also use the component's body to show content on any platform.
3. It's extensible, so you can add this behavior to any other component you have. 

## API

The component's API is pretty straightforward: it has two attributes of type Aura.Component[] called "mobile" and "desktop" which you can use to pass in any content that should be displayed only on one platform. 

### Using deviceDetector inside any other

Here's an example of how you can use this component inside another one where you want to have this component's features: 

```html
<aura:component>

    <c:deviceDetector>
        <!-- Common part. Shown in any platform-->
        <div>
            <h1>You are using deviceDetector by Rodrigo Juliani</h1>
            <span>This content should be shown in both desktop and mobile platforms</span>
        </div>
        <!-- Mobile-only content -->
        <aura:set attribute="mobile">
            <div>
                <h2>You are on mobile</h2>
            </div>
        </aura:set>
        <!-- Desktop-only content -->
        <aura:set attribute="desktop">
            <div>
                <h2>You are on desktop</h2>
            </div>
        </aura:set>
    </c:deviceDetector>
</aura:component>
```