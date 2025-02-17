---
title: リポジトリを検索する
intro: '{% data variables.product.product_name %} 上のリポジトリを検索することができます。そして、これらのリポジトリを検索する修飾子を組み合わせることで、検索結果を絞ることができます。'
redirect_from:
  - /articles/searching-repositories
  - /articles/searching-for-repositories
  - /github/searching-for-information-on-github/searching-for-repositories
  - /github/searching-for-information-on-github/searching-on-github/searching-for-repositories
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - GitHub search
shortTitle: Search for repositories
---

{% data variables.product.product_location %} 全体にわたってグローバルにリポジトリを検索できます。あるいは、特定の Organization のみのリポジトリの検索もできます。 詳細は「[{% data variables.product.prodname_dotcom %} での検索について](/search-github/getting-started-with-searching-on-github/about-searching-on-github)」を参照してください。

フォークを検索結果に含めるためには、クエリに `fork:true` または `fork:only` を追加する必要があります。 詳細は「[フォーク内で検索する](/search-github/searching-on-github/searching-in-forks)」を参照してください。

{% data reusables.search.syntax_tips %}

## リポジトリ名、説明、または README ファイルの内容で検索

With the `in` qualifier you can restrict your search to the repository name, repository description, repository topics, contents of the README file, or any combination of these. When you omit this qualifier, only the repository name, description, and topics are searched.

| 修飾子               | サンプル                                                                                                                                                    |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `in:name`         | [**jquery in:name**](https://github.com/search?q=jquery+in%3Aname&type=Repositories) は、リポジトリ名に「jquery」が含まれるリポジトリにマッチします。                                |
| `in:description`  | [**jquery in:name,description**](https://github.com/search?q=jquery+in%3Aname%2Cdescription&type=Repositories) は、リポジトリ名または説明に「jquery」が含まれるリポジトリにマッチします。 |
| `in:topics`       | [**jquery in:topics**](https://github.com/search?q=jquery+in%3Atopics&type=Repositories) matches repositories labeled with "jquery" as a topic.         |
| `in:readme`       | [**jquery in:readme**](https://github.com/search?q=jquery+in%3Areadme&type=Repositories) は、リポジトリの README ファイルで「jquery」をメンションしているリポジトリにマッチします。           |
| `repo:owner/name` | [**repo:octocat/hello-world**](https://github.com/search?q=repo%3Aoctocat%2Fhello-world) matches a specific repository name.                            |

## リポジトリの内容で検索

`in:readme` 修飾子を使用すると、リポジトリの README ファイルの内容に基づいてリポジトリを検索できます。 詳細は「[README について](/github/creating-cloning-and-archiving-repositories/about-readmes)」を参照してください。

`in:readme` は、特定の内容に基づいてリポジトリを検索する唯一の方法です。 リポジトリ内の特定のファイルや内容を検索するには、ファイルファインダー、またはコード固有の検索修飾子を使います。 詳細は「[ {% data variables.product.prodname_dotcom %}でファイルを検索する](/search-github/searching-on-github/finding-files-on-github)」および「[コードの検索](/search-github/searching-on-github/searching-code)」を参照してください。

| 修飾子         | サンプル                                                                                                                                             |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `in:readme` | [**octocat in:readme**](https://github.com/search?q=octocat+in%3Areadme&type=Repositories) は、リポジトリの README ファイルで「octocat」をメンションしているリポジトリにマッチします。 |

## ユーザまたは Organization のリポジトリ内の検索

特定のユーザまたは Organization のすべてのリポジトリで検索するには、`user` 修飾子または `org` 修飾子を使います。

| 修飾子                       | サンプル                                                                                                                                                               |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <code>user:<em>USERNAME</em></code> | [**user:defunkt forks:&gt;100**](https://github.com/search?q=user%3Adefunkt+forks%3A%3E%3D100&type=Repositories) は、フォーク数が 100 より多い @defunkt からのリポジトリにマッチします。 |
| <code>org:<em>ORGNAME</em></code> | [**org:github**](https://github.com/search?utf8=%E2%9C%93&q=org%3Agithub&type=Repositories) は、GitHub からのリポジトリにマッチします。                                              |

## リポジトリのサイズで検索

`size` 修飾子は、不等号や範囲の修飾子を使うことで、特定のサイズ (キロバイト) に合致するリポジトリを表示します。 詳しい情報については、「[検索構文を理解する](/github/searching-for-information-on-github/understanding-the-search-syntax)」を参照してください。

| 修飾子                       | サンプル                                                                                                                   |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| <code>size:<em>n</em></code> | [**size:1000**](https://github.com/search?q=size%3A1000&type=Repositories) は、ちょうど 1 MB のリポジトリにマッチします。                  |
|                           | [**size:&gt;=30000**](https://github.com/search?q=size%3A%3E%3D30000&type=Repositories) は、30 MB 以上のリポジトリにマッチします。 |
|                           | [**size:&lt;50**](https://github.com/search?q=size%3A%3C50&type=Repositories) は、50 KB 未満のリポジトリにマッチします。           |
|                           | [**size:50..120**](https://github.com/search?q=size%3A50..120&type=Repositories) は、50 KB から 120 KB までのリポジトリにマッチします。    |

## フォロワーの数の検索

`followers` 修飾子と、不等号や範囲の修飾子を使用すると、リポジトリをフォローしているユーザーの数に基づいてリポジトリをフィルタリングできます。 詳しい情報については、「[検索構文を理解する](/github/searching-for-information-on-github/understanding-the-search-syntax)」を参照してください。

| 修飾子                       | サンプル                                                                                                                                                                                              |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <code>followers:<em>n</em></code> | [**node followers:>=10000**](https://github.com/search?q=node+followers%3A%3E%3D10000) は、「node」という単語にメンションしている、10,000 人以上のフォロワーがいるリポジトリにマッチします。                                                   |
|                           | [**styleguide linter followers:1..10**](https://github.com/search?q=styleguide+linter+followers%3A1..10&type=Repositories) は、「styleguide linter」という単語にメンションしている、フォロアーが 1 人から 10 人までのリポジトリにマッチします。 |

## フォークの数で検索

`forks` 修飾子は、不等号や範囲の修飾子を使って、リポジトリが持つべきフォークの数を指定します。 詳しい情報については、「[検索構文を理解する](/github/searching-for-information-on-github/understanding-the-search-syntax)」を参照してください。

| 修飾子                       | サンプル                                                                                                                      |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| <code>forks:<em>n</em></code> | [**forks:5**](https://github.com/search?q=forks%3A5&type=Repositories) は、フォーク数が 5 のリポジトリだけにマッチします。                        |
|                           | [**forks:&gt;=205**](https://github.com/search?q=forks%3A%3E%3D205&type=Repositories) は、フォーク数が 205 以上のリポジトリにマッチします。 |
|                           | [**forks:&lt;90**](https://github.com/search?q=forks%3A%3C90&type=Repositories) は、フォーク数が 90 未満のリポジトリにマッチします。        |
|                           | [**forks:10..20**](https://github.com/search?q=forks%3A10..20&type=Repositories) は、フォーク数が 10 から 20 までのリポジトリにマッチします。       |

## Star の数で検索

不等号や範囲の修飾子を使って、リポジトリの Star の数でリポジトリを検索できます。 詳しい情報については「[Star を付けてリポジトリを保存する](/github/getting-started-with-github/saving-repositories-with-stars)」および「[検索構文を理解する](/github/searching-for-information-on-github/understanding-the-search-syntax)」を参照してください。

| 修飾子                       | サンプル                                                                                                                                                                                               |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <code>stars:<em>n</em></code> | [**stars:500**](https://github.com/search?utf8=%E2%9C%93&q=stars%3A500&type=Repositories) は、Star がちょうど 500 のリポジトリにマッチします。                                                                          |
|                           | [**stars:10..20**](https://github.com/search?q=stars%3A10..20+size%3A%3C1000&type=Repositories) は、1000 KB 未満で、Star が 10 から 20 のリポジトリにマッチします。                                                       |
|                           | [**stars:&gt;=500 fork:true language:php**](https://github.com/search?q=stars%3A%3E%3D500+fork%3Atrue+language%3Aphp&type=Repositories) は、PHP 形式のフォークされたリポジトリを含め Star が 500 以上のリポジトリにマッチします。 |

## リポジトリの作成時期や最終更新時期で検索

作成時期や最終更新時期でリポジトリをフィルタリングできます。 リポジトリの作成時期については、`created` 修飾子を使います。リポジトリの最終更新時期で見つけるには、`pushed` 修飾子を使います。 `pushed` 修飾子は、リポジトリのいずれかのブランチに対する一番最近のコミットでソートされた、リポジトリのリストを表示します。

どちらの修飾子も、パラメータとして日付を使います。 {% data reusables.time_date.date_format %} {% data reusables.time_date.time_format %}

{% data reusables.search.date_gt_lt %}

| 修飾子                       | サンプル                                                                                                                                                                                                      |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <code>created:<em>YYYY-MM-DD</em></code> | [**webos created:&lt;2011-01-01**](https://github.com/search?q=webos+created%3A%3C2011-01-01&type=Repositories) は、2011 年より前に作成された「webos」という単語があるリポジトリにマッチします。                                       |
| <code>pushed:<em>YYYY-MM-DD</em></code> | [**css pushed:&gt;2013-02-01**](https://github.com/search?utf8=%E2%9C%93&q=css+pushed%3A%3E2013-02-01&type=Repositories) は、2013 年 1 月より後にプッシュされた「css」という単語があるリポジトリにマッチします。                          |
|                           | [**case pushed:&gt;=2013-03-06 fork:only**](https://github.com/search?q=case+pushed%3A%3E%3D2013-03-06+fork%3Aonly&type=Repositories) は、2013 年 3 月 6 日以降にプッシュされ、フォークであり、「case」という単語があるリポジトリにマッチします。 |

## 言語で検索

リポジトリのコードの言語に基づいてリポジトリを検索できます。

| 修飾子                       | サンプル                                                                                                                                                                                    |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <code>language:<em>LANGUAGE</em></code> | [**`rails language:javascript`**](https://github.com/search?q=rails+language%3Ajavascript&type=Repositories) matches repositories with the word "rails" that are written in JavaScript. |

## Topics で検索

特定の Topics で分類されたすべてのリポジトリを見つけることができます。 詳細は「[トピックでリポジトリを分類する](/github/administering-a-repository/classifying-your-repository-with-topics)」を参照してください。

| 修飾子                       | サンプル                                                                                                                                                                                        |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <code>topic:<em>TOPIC</em></code> | [**`topic:jekyll`**](https://github.com/search?utf8=%E2%9C%93&q=topic%3Ajekyll&type=Repositories&ref=searchresults) matches repositories that have been classified with the topic "Jekyll." |

## Topics の数で検索

`topics` 修飾子と、不等号や範囲の修飾子を使うと、リポジトリに適用された Topics の数でリポジトリを検索できます。 詳しい情報については「[Topics によるリポジトリの分類](/github/administering-a-repository/classifying-your-repository-with-topics)」および「[検索構文を理解する](/github/searching-for-information-on-github/understanding-the-search-syntax)」を参照してください。

| 修飾子                        | サンプル                                                                                                                                       |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| <code>topics:<em>n</em></code> | [**topics:5**](https://github.com/search?utf8=%E2%9C%93&q=topics%3A5&type=Repositories&ref=searchresults) は、5 つのトピックがあるリポジトリにマッチします。       |
|                            | [**topics:>3**](https://github.com/search?utf8=%E2%9C%93&q=topics%3A%3E3&type=Repositories&ref=searchresults) は、4 つ以上のトピックがあるリポジトリにマッチします。 |

{% ifversion fpt or ghes or ghec %}

## ライセンスで検索

リポジトリのライセンスの種類に基づいてリポジトリを検索できます。 特定のライセンスまたはライセンスファミリーによってリポジトリをフィルタリングするには、ライセンスキーワードを使う必要があります。 詳細は「[リポジトリのライセンス](/github/creating-cloning-and-archiving-repositories/licensing-a-repository)」を参照してください。

| 修飾子                        | サンプル                                                                                                                                                                      |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <code>license:<em>LICENSE_KEYWORD</em></code> | [**license:apache-2.0**](https://github.com/search?utf8=%E2%9C%93&q=license%3Aapache-2.0&type=Repositories&ref=searchresults) は、Apache ライセンス 2.0 によりライセンスされたリポジトリにマッチします。 |

{% endif %}

## リポジトリの可視性で検索

リポジトリの可視性に基づいて検索を絞り込むことができます。 For more information, see "[About repositories](/repositories/creating-and-managing-repositories/about-repositories#about-repository-visibility)."

| Qualifier  | Example | ------------- | ------------- |{% ifversion fpt or ghes or ghec %} | `is:public` | [**is:public org:github**](https://github.com/search?q=is%3Apublic+org%3Agithub&type=Repositories) matches public repositories owned by {% data variables.product.company_short %}.{% endif %}{% ifversion ghes or ghec or ghae %} | `is:internal` | [**is:internal test**](https://github.com/search?q=is%3Ainternal+test&type=Repositories) matches internal repositories that you can access and contain the word "test".{% endif %} | `is:private` | [**is:private pages**](https://github.com/search?q=is%3Aprivate+pages&type=Repositories) matches private repositories that you can access and contain the word "pages."

{% ifversion fpt or ghec %}

## リポジトリがミラーかどうかで検索

リポジトリがミラーか、それ以外にホストされているかに基づいてリポジトリを検索できます。 詳しい情報については、「[{% data variables.product.prodname_dotcom %} でオープンソースにコントリビュートする方法を見つける](/github/getting-started-with-github/finding-ways-to-contribute-to-open-source-on-github)」を参照してください。

| 修飾子            | サンプル                                                                                                                                    |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `mirror:true`  | [**mirror:true GNOME**](https://github.com/search?utf8=%E2%9C%93&q=mirror%3Atrue+GNOME&type=) は、ミラーで「GNOME」という単語を含むリポジトリにマッチします。        |
| `mirror:false` | [**mirror:false GNOME**](https://github.com/search?utf8=%E2%9C%93&q=mirror%3Afalse+GNOME&type=)は、ミラーではなく、かつ「GNOME」という単語を含むリポジトリにマッチします。 |

{% endif %}

## リポジトリがアーカイブされているかどうかで検索

アーカイブされているかどうかでリポジトリを検索できます。 For more information, see "[Archiving repositories](/repositories/archiving-a-github-repository/archiving-repositories)."

| 修飾子              | サンプル                                                                                                                                           |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `archived:true`  | [**archived:true GNOME**](https://github.com/search?utf8=%E2%9C%93&q=archived%3Atrue+GNOME&type=) は、「GNOME」という単語を含むアーカイブされたリポジトリにマッチします。       |
| `archived:false` | [**archived:false GNOME**](https://github.com/search?utf8=%E2%9C%93&q=archived%3Afalse+GNOME&type=) は、「GNOME」という単語を含む、アーカイブされていないリポジトリにマッチします。 |

{% ifversion fpt or ghec %}

## `good first issue` ラベルや `help wanted` ラベルの付いた Issue の数で検索

`help-wanted` ラベルや `good-first-issue` ラベルの付いた Issue の最低数があるリポジトリを、`help-wanted-issues:>n` 修飾子や `good-first-issues:>n` 修飾子によって検索できます。 詳細は、「[ラベルを使用してプロジェクトに役立つコントリビューションを促す](/communities/setting-up-your-project-for-healthy-contributions/encouraging-helpful-contributions-to-your-project-with-labels)」を参照してください。

| 修飾子                        | サンプル                                                                                                                                                                                                                                                   |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `good-first-issues:>n`  | [**`good-first-issues:&gt;2 javascript`**](https://github.com/search?utf8=%E2%9C%93&q=javascript+good-first-issues%3A%3E2&type=) matches repositories with more than two issues labeled `good-first-issue` and that contain the word "javascript." |
| `help-wanted-issues:>n` | [**help-wanted-issues:&gt;4 react**](https://github.com/search?utf8=%E2%9C%93&q=react+help-wanted-issues%3A%3E4&type=) は、「React」という単語を含む、`help-wanted` ラベルが付いた 5 つ以上の Issue のあるリポジトリにマッチします。                                                     |

## Search based on ability to sponsor

You can search for repositories whose owners can be sponsored on {% data variables.product.prodname_sponsors %} with the `is:sponsorable` qualifier. 詳しい情報については「[{% data variables.product.prodname_sponsors %}について](/sponsors/getting-started-with-github-sponsors/about-github-sponsors)」を参照してください。

You can search for repositories that have a funding file using the `has:funding-file` qualifier. For more information, see "[About FUNDING files](/github/administering-a-repository/managing-repository-settings/displaying-a-sponsor-button-in-your-repository#about-funding-files)."

| 修飾子                | サンプル                                                                                                                                                                                  |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `is:sponsorable`   | [**is:sponsorable**](https://github.com/search?q=is%3Asponsorable&type=Repositories) matches repositories whose owners have a {% data variables.product.prodname_sponsors %} profile. |
| `has:funding-file` | [**has:funding-file**](https://github.com/search?q=has%3Afunding-file&type=Repositories) matches repositories that have a FUNDING.yml file.                                           |

{% endif %}

## 参考リンク

- 「[検索結果をソートする](/search-github/getting-started-with-searching-on-github/sorting-search-results/)」
- [フォーク内を検索する](/search-github/searching-on-github/searching-in-forks)
