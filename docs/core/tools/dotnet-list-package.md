---
title: Befehl „dotnet list package“
description: Der Befehl „dotnet list package“ bietet eine praktische Option zum Listen von Pakettverweisen auf ein Projekt oder eine Projektmappe.
ms.date: 06/26/2019
ms.openlocfilehash: 98cc456fff02364310cec98f0282700f7697f07e
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421955"
---
# <a name="dotnet-list-package"></a>dotnet list package

[!INCLUDE [topic-appliesto-net-core-22plus](../../../includes/topic-appliesto-net-core-22plus.md)]

## <a name="name"></a>name

`dotnet list package`: Hiermit listen Sie die Paketverweise für ein Projekt oder eine Projektmappe auf.

## <a name="synopsis"></a>Übersicht

```
dotnet list [<PROJECT>|<SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch] 
   [--include-prerelease] [--include-transitive] [--interactive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a>BESCHREIBUNG

Der Befehl `dotnet list package` bietet eine praktische Option zum Listen aller NuGet-Pakettverweise auf ein bestimmtes Projekt oder eine Projektmappe. Sie müssen zuerst das Projekt erstellen, um die Ressourcen zu haben, die für diesen Befehl zur Verarbeitung benötigt werden. Das folgende Beispiel zeigt die Ausgabe des Befehls `dotnet list package` für das Projekt [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis):

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  0.11.0      0.11.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

Die Spalte **Angefordert** bezieht sich auf die in der Projektdatei angegebene Paketversion und kann ein Bereich sein. Die Spalte **Gelöst** listet die Version auf, die das Projekt gerade verwendet, und ist immer ein Einzelwert. Die Pakete, die ein `(A)` direkt neben ihren Namen anzeigen, repräsentieren [implizite Paketverweise](csproj.md#implicit-package-references), die aus Ihren Projekteinstellungen abgeleitet werden (Typ `Sdk`, Eigenschaft `<TargetFramework>` oder `<TargetFrameworks>`, etc.).

Verwenden Sie die Option `--outdated`, um herauszufinden, ob es neuere Versionen der Pakete gibt, die Sie in Ihren Projekten verwenden. Standardmäßig listet `--outdated` die neuesten stabilen Pakete auf, es sei denn, die gelöste Version ist auch eine Vorabversion. Um Vorabversionen in die Liste neuerer Versionen aufzunehmen, geben Sie auch die Option `--include-prerelease` an. Die folgenden Beispiele zeigen die Ausgabe des Befehls `dotnet list package --outdated --include-prerelease` für das gleiche Projekt wie das vorherige Beispiel:

```output
The following sources were used:
   https://api.nuget.org/v3/index.json

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         0.11.0      0.11.0     1.0.0-preview
```

Wenn Sie herausfinden möchten, ob Ihr Projekt transitive Abhängigkeiten aufweist, verwenden Sie die Option `--include-transitive`. Transitive Abhängigkeiten treten auf, wenn Sie ein Paket zu Ihrem Projekt hinzufügen, das wiederum von einem anderen Paket abhängig ist. Das folgende Beispiel zeigt die Ausgabe des Befehls `dotnet list package --include-transitive` für das Projekt [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin), das Pakete auf oberster Ebene und die von ihnen abhängigen Pakete anzeigt:

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Top-level Package                      Requested                    Resolved
   > Microsoft.NETCore.Platforms    (A)   [3.0.0-preview3.19128.7, )   3.0.0-preview3.19128.7
   > Microsoft.WindowsDesktop.App   (A)   [3.0.0-preview3-27504-2, )   3.0.0-preview3-27504-2

   Transitive Package               Resolved
   > Microsoft.NETCore.Targets      2.0.0
   > PluginBase                     1.0.0

(A) : Auto-referenced package.
```

## <a name="arguments"></a>Argumente

`PROJECT | SOLUTION`

Die zu verwendende Projekt- oder Projektmappendatei. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei. Wenn mehr als eine Projektmappe oder ein Projekt gefunden wird, wird ein Fehler ausgegeben.

## <a name="options"></a>Optionen

* **`--config <SOURCE>`**

  Die bei der Suche nach neueren Paketen zu verwendenden NuGet-Quellen. Hierfür ist die Option `--outdated` erforderlich.

* **`--framework <FRAMEWORK>`**

  Zeigt nur die Pakete an, die für das angegebene [Zielframework](../../standard/frameworks.md) gelten. Um mehrere Frameworks anzugeben, wiederholen Sie die Option mehrmals. Beispiel: `--framework netcoreapp2.2 --framework netstandard2.0`.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`--highest-minor`**

  Hiermit werden bei der Suche nach neueren Paketen nur die Pakete mit übereinstimmender Hauptversionsnummer berücksichtigt. Hierfür ist die Option `--outdated` erforderlich.

* **`--highest-patch`**

  Hiermit werden bei der Suche nach neueren Paketen nur die Pakete mit übereinstimmender Haupt- und Nebenversionsnummer berücksichtigt. Hierfür ist die Option `--outdated` erforderlich.

* **`--include-prerelease`**

  Hiermit werden bei der Suche nach neueren Pakete auch Pakete mit Vorabversionen berücksichtigt. Hierfür ist die Option `--outdated` erforderlich.

* **`--include-transitive`**

  Listet transitive Pakete zusätzlich zu den Paketen auf der obersten Ebene auf. Wenn Sie diese Option angeben, erhalten Sie eine Liste der Pakete, von denen die Pakete auf der obersten Ebene abhängen.

* **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten. Beispielsweise, um die Authentifizierung abzuschließen. Verfügbar seit .NET Core 3.0 SDK.

* **`--outdated`**

  Listet Pakete auf, für die neuere Versionen verfügbar sind.

* **`-s|--source <SOURCE>`**

  Die bei der Suche nach neueren Paketen zu verwendenden NuGet-Quellen. Hierfür ist die Option `--outdated` erforderlich.

## <a name="examples"></a>Beispiele

* Liste der Paketverweise eines bestimmten Projekts:

  ```console
  dotnet list SentimentAnalysis.csproj package
  ```

* Liste von Paketverweisen, für die neuere Versionen verfügbar sind, einschließlich Vorabversionen:

  ```console
  dotnet list package --outdated --include-prerelease
  ```

* Liste von Paketverweisen für ein bestimmtes Zielframework:

  ```console
  dotnet list package --framework netcoreapp3.0
  ```
