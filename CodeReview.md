# Code Review

[https://github.com/ozkanonur/feednext/pull/91](https://github.com/ozkanonur/feednext/pull/91)

## Before code review
Before code review, I'll ask this developer to provide more context.
1. Why make these changes?
2. How to verify changes are run as expected?
3. If have unit test policy, will also ask to follow unit test policy.
4. I'll also ask to avoid large changes, the large changes will make it difficult to merge back to main branches.

## client/next.config.js
[<img src="public/client-next-config-js.png">](
https://github.com/ozkanonur/feednext/pull/91/files#diff-6a52ebdee5662eb75f6f3010d0aca4b33d708e85c7203d00cf50b1109480ae16R15)
* async function not contain an await keyword, should confirm that, add await or remove async 

## client/src/@types/pages/create-feed/index.d.ts
[<img src="public/client-src-types-pages-create-feed-index-d-ts.png">](https://github.com/ozkanonur/feednext/pull/91/files#diff-3aee0b119ee16abf7c3c99ef4c5df45bd54b99202800947299efb72265062373R5)
* The `tags:string` will be confusing. It better change to "tagId": string or "tags": string[]. 

## client/src/pages/[feed]/index.tsx
[<img src="public/client-src-pages-[feed]-index-tsx.png">](https://github.com/ozkanonur/feednext/pull/91/files#diff-b7af3f9a8a559d522f0006dd2dedc26210dd2b42f78d67b4c8e2129191844be8R78-R85)
* handleDeSelect not having return data should also add (): void => {...} 

## client/src/pages/index.tsx
[<img src="public/client-src-pages-index-tsx.png">](https://github.com/ozkanonur/feednext/pull/91/files#diff-9691d47c27ed016e859106bb5803c62dce15c43051caa1670bd753ec97276575R43-R47)
* Didn't see "skipValueForPagination, tagFilter, sortBy, isLoading" use in useEffect, need more comment why make them as useEffect dependency.

[<img src="public/client-src-pages-index-tsx-2.png">]("https://github.com/ozkanonur/feednext/pull/91/files#diff-9691d47c27ed016e859106bb5803c62dce15c43051caa1670bd753ec97276575R60-R72")
* need take care tagFilter here, it's possible to get the wrong variable, could use "useCallback" to fix it. 

## client/src/services/api/Title/index.ts
[<img src="public/client-src-services-api-Title-index-ts.png">](https://github.com/ozkanonur/feednext/pull/91/files#diff-594b2887ab5032e6c5198e63f50531f207cfe7b0054646987769b39e9e0ca613R11-R15)
* using the spread operator here will make it a little weird. Because username, tags, sortBy are all string types, I need more comments here. 

## server/package.json
[<img src="public/server-package-json.png">](https://github.com/ozkanonur/feednext/pull/91/files?diff=unified&w=0#diff-da00458cdaeaea2314cb0e0101c85130593048072ada62de01727958c5d6ca37L35-R35)
* We could take a note, it's to avoid 0.12.0 breaking changes.
* CHANGELOG
   * https://github.com/typestack/class-validator/blob/6a5762196b06655d51dddfff7807a5a87fc12216/CHANGELOG.md

## server/src/v1/Title/Service/title.service.ts
[<img src="public/server-src-v1-title-service-title-service-ts.png">](https://github.com/ozkanonur/feednext/pull/91/files#diff-ae7847f28809ea43b2bb4fdc75bc32829ee8fa79bff9ac012a3f50a63ebb6e10R96)
[<img src="public/server-src-v1-title-service-title-service-ts-2.png">](https://github.com/ozkanonur/feednext/pull/91/files#diff-ae7847f28809ea43b2bb4fdc75bc32829ee8fa79bff9ac012a3f50a63ebb6e10R165-R166)
* should remove async, and improve with sql batch update solution to speed performance.
* typeorm bulk update via raw query
   * https://stackoverflow.com/questions/53790994/bulk-update-via-raw-query-in-typeorm

## avoid use if single line.
The if single line statement easily makes errors, when you do copy and paste.
