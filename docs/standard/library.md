---
title: .NET-Standardbibliothek
description: .NET-Standardbibliothek
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
translationtype: Human Translation
ms.sourcegitcommit: 633dcc6d966125139cb21c4e70dac4d4794ee9a4
ms.openlocfilehash: da326fb823c16c7795a6a05ad302c13918b435aa
ms.lasthandoff: 03/20/2017

---

# <a name="net-standard-library"></a>.NET-Standardbibliothek

Die .NET-Standardbibliothek ist eine formale Spezifikation von .NET-APIs, die für alle .NET-Laufzeiten verfügbar sein sollen. Die Motivation hinter der Standardbibliothek ist das Herstellen einer umfassenderen Einheitlichkeit im .NET-Ökosystem. Auch wenn [ECMA-335](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) weiterhin für Einheitlichkeit im .NET-Laufzeitverhalten sorgt, gibt es keine ähnliche Spezifikation für die .NET-Basisklassenbibliotheken (BCL) für Implementierungen der .NET-Bibliothek. 

Die .NET-Standardbibliothek ermöglicht im Wesentlichen die folgenden Szenarios: 

- Sie definiert einen einheitlichen Satz von BCL-APIs, die unabhängig von der Arbeitsauslastung für alle .NET-Plattformen implementiert werden.
- Sie ermöglicht Entwicklern die Erstellung portabler Bibliotheken, die anhand desselben Satzes von APIs übergreifend über .NET-Runtimes hinweg eingesetzt werden können.
- Sie reduziert und beseitigt idealerweise die bedingte Kompilierung freigegebener Quellen aufgrund von .NET-APIs (nur für Betriebssystem-APIs).

Die verschiedenen .NET-Runtimes implementieren bestimmte Versionen der .NET-Standardbibliothek. Jede .NET-Runtimeversion kündigt die höchste .NET-Standardversion an, die von ihr unterstützt wird, was bedeutet, dass sie auch frühere Versionen unterstützt. .NET Framework 4.6 implementiert z.B. die .NET-Standardbibliothek 1.3 und macht damit alle APIs verfügbar, die in den Versionen 1.0 bis 1.3 der .NET-Standardbibliotheken definiert sind. Auf ähnliche Weise implementiert .NET Framework 4.6.2 die .NET-Standardbibliothek 1.5, während .NET Core 1.0 die .NET-Standardbibliothek 1.6 implementiert.

## <a name="net-platforms-support"></a>Unterstützung für .NET-Plattformen

Hier sehen Sie den vollständigen Satz von .NET-Runtimes, die die .NET-Standardbibliothek unterstützen.

| Plattformname | Alias |  |  |  |  |  | | | |
| :---------- | :--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |
|.NET-Standard | netstandard | 1,0 | 1,1 | 1.2 | 1.3 | 1.4 | 1.5 | 1.6 | 2,0 |
|.NET Core|netcoreapp|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|1,0|2.0|
|.NET Framework|net|&rarr;|4.5|4.5.1|4.6|4.6.1|4.6.2|vNext|4.6.1|
|Mono-/Xamarin-Plattformen||&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|vNext|
|Universelle Windows-Plattform|uap|&rarr;|&rarr;|&rarr;|&rarr;|10.0|&rarr;|&rarr;|vNext|
|Windows|win|&rarr;|8.0|8.1||||||
|Windows Phone|wpa|&rarr;|&rarr;|8.1||||||
|Windows Phone Silverlight|wp|8.0||||||||

## <a name="comparison-to-portable-class-libraries"></a>Vergleich mit portablen Klassenbibliotheken

Die .NET-Standardbibliothek kann man sich als die nächste Generation [portabler Klassenbibliotheken (PCL)](https://msdn.microsoft.com/library/gg597391.aspx) vorstellen. Die .NET-Standardbibliothek profitiert von der Erfahrung mit der Erstellung portabler Bibliotheken, indem eine Standard-BCL zusammengestellt und damit eine umfassendere Einheitlichkeit über .NET-Runtimes hinweg hergestellt wird. Eine Bibliothek, die die .NET-Standardbibliothek als Ziel verwendet, ist eine PCL oder eine „auf dem .NET-Standard basierende PCL“. Vorhandene PCLs werden als „profilbasierte PCLs“ bezeichnet.

Die .NET-Standardbibliothek und PCL-Profile wurden zu ähnlichen Zwecke erstellt, unterscheiden sich jedoch in wesentlichen Bereichen.

Ähnlichkeiten:

- Definiert die APIs, die zur Freigabe von binärem Code verwendet werden können.

Unterschiede:

- Die .NET-Standardbibliothek ist ein zusammengestellter Satz von APIs, während PCL-Profile durch Schnittpunkte vorhandener Plattformen definiert werden.
- Die .NET-Standardbibliothek weist im Gegensatz zu PCL-Profilen eine lineare Versionierung auf.
- PCL-Profile stehen für Microsoft-Plattformen, während die .NET-Standardbibliothek plattformunabhängig ist.

## <a name="specification"></a>Spezifikation

Die Spezifikation der .NET-Standardbibliothek ist ein standardisierter Satz von APIs. Die Spezifikation wird durch Implementierungen der .NET-Runtime verwaltet, insbesondere Microsoft (einschließlich .NET Framework, .NET Core und Mono) und Unity. Im Rahmen der Einrichtung neuer Versionen der .NET-Standardbibliothek wird ein öffentlicher Feedbackprozess verwendet.

### <a name="official-artifacts"></a>Offizielle Artefakte

Die offizielle Spezifikation ist ein Satz von CS-Dateien zur Definition der APIs, die Bestandteile des Standards sind. Das [ref-Verzeichnis](https://github.com/dotnet/corefx/tree/master/src/System.Runtime/ref) für jede [Komponente](https://github.com/dotnet/corefx/tree/master/src) definiert die APIs der .NET-Standardbibliothek. Auch wenn sich die ref-Artefakte im [CoreFX-Repository](https://github.com/dotnet/corefx) befinden, sind sie nicht .NET Core-spezifisch.

Das [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library)-Metapaket ([Quelle](https://github.com/dotnet/standard/blob/master/netstandard/pkg/NETStandard.Library.dependencies.props)) beschreibt den Satz von Bibliotheken, die (teilweise) eine oder mehrere Versionen der .NET-Standardbibliothek definieren.

Eine bestimmte Komponente, wie System.Runtime, beschreibt Folgendes:

- Teil der .NET-Standardbibliothek (nur der Bereich).
- Mehrere Versionen der .NET-Standardbibliothek für diesen Bereich.

Abgeleitete Elemente werden bereitgestellt, um ein einfacheres Lesen und bestimmte Entwicklungsszenarios (z.B. die Verwendung eines Compilers) zu ermöglichen.

- API-Liste in Markdown (TBD)
- Referenzassemblys, die als [NuGet-Pakete](../core/packages.md) verteilt und vom Metapaket [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/) referenziert werden.

### <a name="package-representation"></a>Paketdarstellung

Das primäre Verteilungsinstrument für die .NET-Standardbibliothek sind [NuGet-Pakete](../core/packages.md). Implementierungen werden in einer Vielzahl von Methoden abgeleitet, die jeweils für die einzelnen .NET-Runtimes geeignet sind.

NuGet-Pakete sind auf mindestens ein [Framework](frameworks.md) ausgerichtet. Die Pakete der .NET-Standardbibliothek sind für das Framework „.NET Standard“ ausgelegt. Sie können über den [komprimierten TFM](frameworks.md) `netstandard` (z.B. `netstandard1.4`) das .NET Standard Framework als Ziel angeben. Bibliotheken, die auf mehreren Runtimes ausgeführt werden sollen, sollten dieses Framework als Ziel verwenden. 

Das Metapaket `NETStandard.Library` verweist auf den vollständigen Satz von NuGet-Paketen, die die .NET-Standardbibliothek definieren.  Die gängigste Methode, `netstandard` als Ziel auszuwählen, ist das Verweisen auf dieses Metapaket. Es beschreibt und bietet Zugriff auf etwa&40; .NET-Bibliotheken und zugehörige APIs, die die .NET-Standardbibliothek definieren. Sie können auf zusätzliche Pakete verweisen, die `netstandard` als Ziel verwenden, um Zugriff auf weitere APIs zu erhalten. 

### <a name="versioning"></a>Versionskontrolle

Die Spezifikation ist nicht singulär, sondern ein ständig wachsender und linear versionierter Satz von APIs. In der ersten Version des Standards wird ein Basissatz von APIs eingerichtet. Nachfolgende Versionen fügen APIs hinzu und erben APIs, die in früheren Versionen definiert wurden. Es gibt keine festgelegte Möglichkeit zum Entfernen von APIs aus dem Standard.

Die .NET-Standardbibliothek ist weder spezifisch auf eine bestimmte .NET-Runtime ausgelegt, noch entspricht sie dem Versionierungsschema einer dieser Runtimes.

APIs, die einer der Laufzeiten (z.B. .NET Framework, .NET Core und Mono) hinzugefügt werden, können als Kandidaten für die Spezifikation betrachtet werden, insbesondere, wenn sie von grundlegender Natur sind. Neue [Versionen der .NET-Standardbibliothek](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/net-platform-standard.md#list-of-net-corefx-apis-and-their-associated-net-platform-standard-version) werden basierend auf .NET-Runtimeversionen erstellt, sodass Sie neue APIs über eine .NET-Standard-PCL adressieren können. Die Mechanismen der Versionskontrolle werden ausführlich unter [.NET Core-Versionskontrolle](../core/versions/index.md) beschrieben.

Die Versionskontrolle der .NET-Standardbibliothek ist wichtig für die Nutzung. Mit einer bestimmten Version der .NET-Standardbibliothek können Sie Bibliotheken verwenden, die auf dieselbe oder eine niedrigere Version ausgerichtet sind. Die folgende Vorgehensweise beschreibt den Workflow für die Verwendung von PCLs der .NET-Standardbibliothek, die auf die .NET-Standardbibliothek ausgerichtet sind.

- Wählen Sie eine Version der .NET-Standardbibliothek für Ihre PCL.
- Verwenden Sie Bibliotheken, die von derselben oder einer niedrigeren Version der .NET-Standardbibliothek abhängig sind.
- Wenn Sie eine Bibliothek finden, die von einer höheren Version der .NET-Standardbibliothek abhängig ist, müssen Sie entweder dieselbe Version implementieren oder von der Verwendung dieser Bibliothek absehen.

### <a name="pcl-compatibility"></a>PCL-Kompatibilität

Die .NET-Standardbibliothek ist mit einer Teilmenge von PCL-Profilen kompatibel. Die .NET-Standardbibliotheken der Versionen 1.0, 1.1 und 1.2 überschneiden sich jeweils mit einem Satz von PCL-Profilen. Diese Überschneidung wurde aus zwei Gründen erstellt:

- Auf dem .NET-Standard basierende PCLs können auf profilbasierte PCLs verweisen.
- Profilbasierte PCLs können als auf dem .NET-Standard basierende PCLs paketiert werden.

Die Kompatibilität profilbasierter PCLs wird über das NuGet-Paket [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) gewährleistet. Diese Abhängigkeit ist erforderlich, wenn Sie auf NuGet-Pakete verweisen, die profilbasierte PCLs enthalten.

Profilbasierte PCLs, die als `netstandard` paketiert wurden, sind einfacher zu verwenden als normal paketierte profilbasierte PCLs. `netstandard`-Verpackung ist mit vorhandenen Benutzern kompatibel.

Sehen Sie sich den Satz von PCL-Profilen an, die mit dem .NET-Standard kompatibel sind: 

| Profile | Version des .NET-Plattformstandards |
| ---------| --------------- |
| Profile7 .NET Portable Subset (.NET Framework 4.5, Windows 8) | 1,1 |
| Profile31 .NET Portable Subset (Windows 8.1, Windows Phone Silverlight 8.1)| 1,0 |
| Profile32 .NET Portable Subset (Windows 8.1, Windows Phone 8.1) | 1.2 |
| Profile44 .NET Portable Subset (.NET Framework 4.5.1, Windows 8.1) | 1.2 |
| Profile49 .NET Portable Subset (.NET Framework 4.5, Windows Phone Silverlight 8) | 1,0 |
| Profile78 .NET Portable Subset (.NET Framework 4.5, Windows 8, Windows Phone Silverlight 8) | 1,0 |
| Profile84 .NET Portable Subset (Windows Phone 8.1, Windows Phone Silverlight 8.1) | 1,0 |
| Profile111 .NET Portable Subset (.NET Framework 4.5, Windows 8, Windows Phone 8.1) | 1,1 |
| Profile151 .NET Portable Subset (.NET Framework 4.5.1, Windows 8.1, Windows Phone 8.1) | 1.2 |
| Profile157 .NET Portable Subset (Windows 8.1, Windows Phone 8.1, Windows Phone Silverlight 8.1) | 1,0 |
| Profile259 .NET Portable Subset (.NET Framework 4.5, Windows 8, Windows Phone 8.1, Windows Phone Silverlight 8) | 1,0 |

## <a name="targeting-net-standard-library"></a>Festlegen der .NET-Standardbibliothek als Ziel

Sie können .NET-Standardbibliotheken anhand einer Kombination aus dem `netstandard`-Framework und dem NETStandard.Library-Metapaket [erstellen](../core/tutorials/libraries.md). Sehen Sie sich Beispiele dafür an, wie [die .NET-Standardbibliothek mithilfe von .NET Core-Tools als Ziel festgelegt wird](../core/packages.md).

