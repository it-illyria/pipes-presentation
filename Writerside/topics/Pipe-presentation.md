# Angular Pipes Presentation

## Introduction

Welcome to the documentation on Pipes in Angular 17! Pipes are a powerful feature in Angular that allows you to transform and format data in your templates. In this presentation, we'll explore the basics of Angular 17 Pipes and how you can leverage them to enhance the user experience.

## Table of Contents

1. [What are Pipes?](#what-are-pipes)
2. [Built-in Pipes](#built-in-pipes)
3. [Custom Pipes](#custom-pipes)
4. [Async Pipes](#async-pipes)
5. [Chaining Pipes](#chaining-pipes)
6. [Pure and Impure Pipes](#pure-and-impure-pipes)
7. [Conclusion](#conclusion)

## What are Pipes?

Pipes are a way to transform data in your Angular templates. They allow you to format and manipulate data before it's displayed to the user. Angular provides a set of built-in pipes, and you can also create your own custom pipes.

## Built-in Pipes

Angular comes with a variety of built-in pipes for common use cases, such as date formatting, number formatting, and more. Some examples include:

- `{{ value | date }}`: Formats a date.
- `{{ value | currency }}`: Formats a number as currency.
- `{{ value | uppercase }}`: Converts a string to uppercase.
- `{{ value | lowercase }}`: Converts a string to lowercase.

## Where can we use pipes:

- ## Custom Pipes

You can create your own custom pipes to suit the specific needs of your application. Custom pipes are reusable and can be applied to different data sets. Here's a basic structure of a custom pipe:

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'customPipe'
})
export class CustomPipe implements PipeTransform {
  transform(value: any, args?: any): any {
    // Custom logic goes here
    return transformedValue;
  }
}
```

- ## Async Pipes
The Async Pipe is a special built-in pipe designed to work with Observables. It automatically subscribes to an Observable and returns the latest value emitted.

```html
{{ data$ | async }}
```

- ## Chaining Pipes

You can chain multiple pipes together to create more complex transformations. The order of the pipes matters, as data is passed through each pipe in sequence.

```html
{{ value | uppercase | customPipe | date }}
```
- ## Pure and Impure Pipes

Understanding the concept of pure and impure pipes is crucial. Pure pipes are stateless and only recalculate when the input values change. Impure pipes, on the other hand, recalculate on every change detection cycle. Use them wisely to optimize performance.

## Conclusion

In conclusion, Angular 17 Pipes are a powerful tool for transforming and formatting data in your application. Whether you're using built-in pipes or creating custom ones, they provide a clean and efficient way to enhance the user interface.

___

> Happy Coding!


<tabs>
    <tab title="custom.pipe.ts">
        <code-block lang="typescript">
            <![CDATA[

                import { Pipe, PipeTransform } from '@angular/core';

                @Pipe({
                    name: 'heroTrail'
                })
                export class HeroTrailPipe implements PipeTransform {
                    transform(heroName: string): string {
                        return `${heroName} - Go to the Hero Trail!`;
                    }
                }
            ]]>
</code-block>
    </tab>
    <tab title="app.component.ts">
        <code-block lang="typescript">
            <![CDATA[
                import { Component } from '@angular/core';

                @Component({
                selector: 'app-root',
                templateUrl: './app.component.html',
                styleUrls: './app.component.scss',
                })
                
                export class AppComponent {}
]]>
</code-block>
    </tab>
    <tab title="app.component.html">
        <code-block lang="html"> 
            <![CDATA[
                <div>
                    <h2>{{ 'Spider-Man' | heroTrail }}</h2>
                    <p>{{ 'Iron Man' | heroTrail }}</p>
                </div>
            ]]>
        </code-block>
    </tab>
</tabs>
