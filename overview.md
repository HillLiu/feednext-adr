# Overview

## Review project
  * [feednext](https://github.com/ozkanonur/feednext)

## Propose top 1-3 initiatives
  * [Simplify Environment](simplify-env-001.md)
  * [Add Measurement](add-measurement-001.md) 
  * [Add Testing](add-testing-001.md) 

```plantuml
@startgantt
saturday are closed
sunday are closed
Project starts 2022-09-01 
[Simplify Environment] lasts 8 days
[Add Measurement] lasts 10  days
[Add Client Testing] lasts 10 days
[Add End2End Testing] lasts 5 days
[Add Server Testing] lasts 5 days
[Add Measurement] starts at [Simplify Environment]'s end
[Add Client Testing] starts at [Add Measurement]'s end
[Add End2End Testing] starts at [Add Client Testing]'s end
[Add Server Testing] starts at [Add End2End Testing]'s end
[Tag AI] starts at [Add Server Testing]'s end
[Simplify Environment] is colored in Fuchsia/FireBrick
[Add Measurement] is colored in GreenYellow/Green
[Tag AI] is colored in LightYellow/Lime
@endgantt
```

```plantuml
@startgantt
saturday are closed
sunday are closed
Project starts 2022-10-25 
[Tag AI-fileter data] lasts 10 days
[Tag AI-train model] lasts 10 days
[Tag AI-tune model] lasts 5 days
[Integration] lasts 3 days
[Tag AI-train model] starts at [Tag AI-fileter data]'s end
[Tag AI-tune model] starts at [Tag AI-train model]'s end
[Integration] starts at [Tag AI-tune model]'s end
[Tag AI-fileter data] is colored in LightYellow/Lime
[Tag AI-train model] is colored in LightYellow/Lime
[Tag AI-tune model] is colored in LightYellow/Lime
@endgantt
```

## Assignment
  * [Link](https://gist.github.com/WhiteHsu/6f490356f9b07a7fab13d1b8591e4672)
