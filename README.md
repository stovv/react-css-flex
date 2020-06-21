# @react-css/flex

A thin wrapper to help make CSS Flexbox simpler and more expressive

[![Build Status](https://travis-ci.org/bikk-uk/react-css-flex.svg?branch=master)](https://travis-ci.org/bikk-uk/react-css-flex)
[![Coverage Status](https://coveralls.io/repos/github/bikk-uk/react-css-flex/badge.svg?branch=master)](https://coveralls.io/github/bikk-uk/react-css-flex?branch=master)
[![Known Vulnerabilities](https://snyk.io/test/github/bikk-uk/react-css-flex/badge.svg?targetFile=package.json)](https://snyk.io/test/github/bikk-uk/react-css-flex?targetFile=package.json)
![GitHub package.json version](https://img.shields.io/github/package-json/v/bikk-uk/react-css-flex?label=github)
![npm](https://img.shields.io/npm/v/@react-css/flex)
![NPM](https://img.shields.io/npm/l/@react-css/flex)

## Getting Started

Installation:

`yarn add @react-css/flex`

`npm install @react-css/flex`

Importing:

```typescript
import Flex from '@react-css/flex'
```

## Usage

All components are `<div />`s with the React props fully exposed.

### Flex

To get a basic Flexbox:

```tsx
<Flex>
  <MyComponent />
</Flex>
```

#### Inline

For an inline Flexbox:

```tsx
<Flex inline>
  <MyComponent />
</Flex>
```

#### Flex Direction

To modify `flex-direction` _(with `React.CSSProperties` types)_:

```tsx
<Flex flexDirection='row'>
  <MyComponent />
</Flex>
```

To simplify, you can use:

```tsx
<Flex row></Flex> // flex-direction: row;
<Flex rowReverse></Flex> // flex-direction: row-reverse;
<Flex column></Flex> // flex-direction: column;
<Flex columnReverse></Flex> // flex-direction: column-reverse;
```

_These are first come first served, in this order. They will be ignored if you provide it manually via the full `flexDirection` prop._

#### Flex Wrap

To modify `flex-wrap` _(with `React.CSSProperties` types)_:

```tsx
<Flex flexWrap='nowrap'>
  <MyComponent />
</Flex>
```

To simplify, you can use:

```tsx
<Flex wrap></Flex> // flex-wrap: wrap;
<Flex noWrap></Flex> // flex-wrap: nowrap;
<Flex wrapReverse></Flex> // flex-wrap: wrap-reverse;
```

_These are first come first served, in this order. They will be ignored if you provide it manually via the full `flexWrap` prop._

#### Justify Content

To modify `justify-content` _(with `React.CSSProperties` types)_:

```tsx
<Flex justifyContent='center'>
  <MyComponent />
</Flex>
```

To simplify, you can use:

```tsx
<Flex justifyStart></Flex> // justify-content: flex-start;
<Flex justifyEnd></Flex> // justify-content: flex-end;
<Flex justifyCenter></Flex> // justify-content: center;
<Flex justifySpaceBetween></Flex> // justify-content: space-between;
<Flex justifySpaceAround></Flex> // justify-content: space-around;
```

_These are first come first served, in this order. They will be ignored if you provide it manually via the full `justifyContent` prop._

#### Align Items

To modify `align-items` _(with `React.CSSProperties` types)_:

```tsx
<Flex alignItems='baseline'>
  <MyComponent />
</Flex>
```

To simplify, you can use:

```tsx
<Flex alignItemsStart></Flex> // align-items: flex-start;
<Flex alignItemsEnd></Flex> // align-items: flex-end;
<Flex alignItemsCenter></Flex> // align-items: center;
<Flex alignItemsBaseline></Flex> // align-items: baseline;
<Flex alignItemsStretch></Flex> // align-items: stretch;
```

_These are first come first served, in this order. They will be ignored if you provide it manually via the full `alignItems` prop._

#### Align Content

To modify `align-content` _(with `React.CSSProperties` types)_:

```tsx
<Flex alignContent='flex-end'>
  <MyComponent />
</Flex>
```

To simplify, you can use:

```tsx
<Flex alignContentStart></Flex> // align-content: flex-start;
<Flex alignContentEnd></Flex> // align-content: flex-end;
<Flex alignContentCenter></Flex> // align-content: center;
<Flex alignContentSpaceBetween></Flex> // align-content: space-between;
<Flex alignContentSpaceAround></Flex> // align-content: space-around;
<Flex alignContentStretch></Flex> // align-content: stretch;
```

_These are first come first served, in this order. They will be ignored if you provide it manually via the full `alignContent` prop._

#### Flex Flow (Shorthand)

To modify `flex-direction` _(with `React.CSSProperties` types)_:

```tsx
<Flex flow='row nowrap'>
  <MyComponent />
</Flex>
```

_The React TypeScript definitions (or underlying [csstype](https://www.npmjs.com/package/csstype) package) unfortunately adds very little type support for this value._

### Flex Items

To help with laying out your components, a Flex Item is also available.

```tsx
<Flex column alignItemsCenter>
  <Flex.Item>
    <MyFirstComponent />
  </Flex.Item>
  <Flex.Item>
    <MySecondComponent />
  </Flex.Item>
</Flex>
```

_**Note**: At this time `<Flex.Item />` is purely syntactic sugar, available to make the structure of the component clearer. It will behave like (and is) a `<div />` with all the TypeScript definitions. Development is ongoing to add support for the Flex Item properties. For now you can just apply them via the usual React styles:_

```tsx
<Flex>
  <Flex.Item
    style={{
      flexGrow: 2,
    }}>
    <MyFirstComponent />
  </Flex.Item>
</Flex>
```

## Notes

All the React `div` props and TypeScript definitions are exposed/passed through. This allows for an identical development experience whilst being able to ignore any Flexbox related CSS.

```tsx
<Flex
  onMouseEnter={onMouseEnter}
  style={{
    background: 'red',
  }}>
  <MyComponent />
</Flex>
```

CSS provided via `styles` will be applied last, this allows all generated CSS to be overridden.

```tsx
<Flex
  inline // this will get overridden
  style={{
    display: 'flex', // this will override everything else
  }}>
  <MyComponent />
</Flex>
```
