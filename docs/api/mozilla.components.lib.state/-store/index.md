[android-components](../../index.md) / [mozilla.components.lib.state](../index.md) / [Store](./index.md)

# Store

`open class Store<S : `[`State`](../-state.md)`, A : `[`Action`](../-action.md)`>` [(source)](https://github.com/mozilla-mobile/android-components/blob/master/components/lib/state/src/main/java/mozilla/components/lib/state/Store.kt#L40)

A generic store holding an immutable [State](../-state.md).

The [State](../-state.md) can only be modified by dispatching [Action](../-action.md)s which will create a new state and notify all registered
[Observer](../-observer.md)s.

### Parameters

`initialState` - The initial state until a dispatched [Action](../-action.md) creates a new state.

`reducer` - A function that gets the current [State](../-state.md) and [Action](../-action.md) passed in and will return a new [State](../-state.md).

### Types

| Name | Summary |
|---|---|
| [Subscription](-subscription/index.md) | `class Subscription<S : `[`State`](../-state.md)`, A : `[`Action`](../-action.md)`>`<br>A [Subscription](-subscription/index.md) is returned whenever an observer is registered via the [observeManually](observe-manually.md) method. Calling [unsubscribe](-subscription/unsubscribe.md) on the [Subscription](-subscription/index.md) will unregister the observer. |

### Constructors

| Name | Summary |
|---|---|
| [&lt;init&gt;](-init-.md) | `Store(initialState: `[`S`](index.md#S)`, reducer: `[`Reducer`](../-reducer.md)`<`[`S`](index.md#S)`, `[`A`](index.md#A)`>)`<br>A generic store holding an immutable [State](../-state.md). |

### Properties

| Name | Summary |
|---|---|
| [state](state.md) | `val state: `[`S`](index.md#S)<br>The current [State](../-state.md). |

### Functions

| Name | Summary |
|---|---|
| [dispatch](dispatch.md) | `fun dispatch(action: `[`A`](index.md#A)`): Job`<br>Dispatch an [Action](../-action.md) to the store in order to trigger a [State](../-state.md) change. |
| [observeManually](observe-manually.md) | `fun observeManually(observer: `[`Observer`](../-observer.md)`<`[`S`](index.md#S)`>): `[`Subscription`](-subscription/index.md)`<`[`S`](index.md#S)`, `[`A`](index.md#A)`>`<br>Registers an [Observer](../-observer.md) function that will be invoked whenever the [State](../-state.md) changes. |

### Extension Functions

| Name | Summary |
|---|---|
| [observe](../../mozilla.components.lib.state.ext/observe.md) | `fun <S : `[`State`](../-state.md)`, A : `[`Action`](../-action.md)`> `[`Store`](./index.md)`<`[`S`](../../mozilla.components.lib.state.ext/observe.md#S)`, `[`A`](../../mozilla.components.lib.state.ext/observe.md#A)`>.observe(owner: LifecycleOwner, observer: `[`Observer`](../-observer.md)`<`[`S`](../../mozilla.components.lib.state.ext/observe.md#S)`>): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html)<br>Registers an [Observer](../-observer.md) function that will be invoked whenever the state changes. The [Store.Subscription](-subscription/index.md) will be bound to the passed in [LifecycleOwner](#). Once the [Lifecycle](#) state changes to DESTROYED the [Observer](../-observer.md) will be unregistered automatically.`fun <S : `[`State`](../-state.md)`, A : `[`Action`](../-action.md)`> `[`Store`](./index.md)`<`[`S`](../../mozilla.components.lib.state.ext/observe.md#S)`, `[`A`](../../mozilla.components.lib.state.ext/observe.md#A)`>.observe(view: <ERROR CLASS>, observer: `[`Observer`](../-observer.md)`<`[`S`](../../mozilla.components.lib.state.ext/observe.md#S)`>): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html)<br>Registers an [Observer](../-observer.md) function that will be invoked whenever the state changes. The [Store.Subscription](-subscription/index.md) will be bound to the passed in [View](#). Once the [View](#) gets detached the [Observer](../-observer.md) will be unregistered automatically. |
| [observeForever](../../mozilla.components.lib.state.ext/observe-forever.md) | `fun <S : `[`State`](../-state.md)`, A : `[`Action`](../-action.md)`> `[`Store`](./index.md)`<`[`S`](../../mozilla.components.lib.state.ext/observe-forever.md#S)`, `[`A`](../../mozilla.components.lib.state.ext/observe-forever.md#A)`>.observeForever(observer: `[`Observer`](../-observer.md)`<`[`S`](../../mozilla.components.lib.state.ext/observe-forever.md#S)`>): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html)<br>Registers an [Observer](../-observer.md) function that will observe the store indefinitely. |

### Inheritors

| Name | Summary |
|---|---|
| [BrowserStore](../../mozilla.components.browser.state.store/-browser-store/index.md) | `class BrowserStore : `[`Store`](./index.md)`<`[`BrowserState`](../../mozilla.components.browser.state.state/-browser-state/index.md)`, `[`BrowserAction`](../../mozilla.components.browser.state.action/-browser-action.md)`>`<br>The [BrowserStore](../../mozilla.components.browser.state.store/-browser-store/index.md) holds the [BrowserState](../../mozilla.components.browser.state.state/-browser-state/index.md) (state tree). |