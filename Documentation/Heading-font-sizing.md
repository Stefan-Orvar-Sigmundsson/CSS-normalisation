[Table of contents](https://github.com/Stefan-Orvar-Sigmundsson/CSS-normalisation/)

# Heading font sizing

Headings (`h1`–`h6`) are given consistent, scaled font sizes that range from `2rem` to `1rem`. This means that `h1` is twice the size of `h6` which matches the font size of paragraphs (`p`). For web projects that for instance only ever use the top three heading levels (`h1`–`h3`), a more drastic scaling may be appropriate.

## Example 1

In this example, `h1` is styled like `h1` in the normalisation style sheet, `h2` like `h3` and `h3` like `h5`.

```
h1
{
	font-size: 2rem;
	line-height: 2.2rem;
	margin-block: 1rem;
}

h2
{
	font-size: 1.6rem;
	line-height: 1.8rem;
	margin-block: 1rem;
}

h3
{
	font-size: 1.2rem;
	line-height: 1.4rem;
	margin-block: 1rem;
}
```

## Example 2

In this example, `h1` is styled like `h2` in the normalisation style sheet, `h2` like `h3` and `h3` like `h6`.

```
h1
{
	font-size: 1.8rem;
	line-height: 2rem;
	margin-block: 1rem;
}

h2
{
	font-size: 1.4rem;
	line-height: 1.6rem;
	margin-block: 1rem;
}

h3
{
	font-size: 1rem;
	line-height: 1.2rem;
	margin-block: 1rem;
}
```