---
title: Typanbieter
description: Erfahren Sie, wie ein F#-Typanbieter eine Komponente ist, die Typen, Eigenschaften und Methoden zur Verwendung in Ihren Programmen bereitstellt.
ms.date: 04/02/2018
ms.openlocfilehash: eae64d2e318ee93f0b8d5b91f0c6da6c91743527
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202108"
---
# <a name="type-providers"></a>Typanbieter

Ein F#-Typanbieter ist eine Komponente, die Typen, Eigenschaften und Methoden zur Verwendung im Programm bereitstellt. Typanbieter generieren **bereitgestellte Typen**, die vom F#-Compiler generiert werden und auf einer externen Datenquelle basieren.

Beispielsweise kann ein F#-Typanbieter für SQL Typen generieren, die Tabellen und Spalten in einer relationalen Datenbank darstellen. Tatsächlich ist dies, was der [SQLProvider](https://fsprojects.github.io/SQLProvider/)-Typanbieter macht.

Bereitgestellte Typen hängen von Eingabeparametern an einen Typanbieter ab. Eine solche Eingabe kann eine Beispieldatenquelle (z. B. eine JSON-Schemadatei), eine URL, die direkt auf einen externen Dienst verweist, oder eine Verbindungszeichenfolge für eine Datenquelle sein. Ein Typanbieter kann außerdem sicherstellen, dass Gruppen von Typen nur bei Bedarf erweitert werden; das heißt, sie werden erweitert, wenn das Programm tatsächlich auf die Typen verweist. Dies ermöglicht die direkte, bedarfsabhängige und stark typisierte Integration von umfangreichen Informationsquellen, z. B. Onlinedatenanbietern.

## <a name="generative-and-erased-type-providers"></a>Generative und gelöschte Typanbieter

Typanbieter gibt es in zwei Arten: generativ und gelöscht.

Generative Typanbieter erzeugen Typen, die als .NET-Typen in die Assembly geschrieben werden können, in der sie erstellt werden. Dies ermöglicht, dass sie von Code in anderen Assemblys genutzt werden können. Dies bedeutet, dass die typisierte Darstellung der Datenquelle in der Regel eine sein muss, die mit .NET-Typen dargestellt werden kann.

Löschende Typanbieter erzeugen Typen, die nur in der Assembly oder in dem Projekt verwendet werden können, in der/dem sie generiert werden. Die Typen sind kurzlebig, was heißt, dass sie nicht in eine Assembly geschrieben werden und nicht von Code in anderen Assemblys verwendet werden können. Sie können *verzögerte* Member enthalten, was es Ihnen erlaubt, bereitgestellte Typen aus einem potenziell unendlichen Informationsbereich zu verwenden. Sie sind nützlich, um eine kleine Teilmenge einer großen und verbundenen Datenquelle zu verwenden.

## <a name="commonly-used-type-providers"></a>Häufig verwendete Typanbieter

Die folgenden weit verbreitet eingesetzten Bibliotheken enthalten Typanbieter für unterschiedliche Verwendungszwecke:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) umfasst Typanbieter für JSON-, XML-, CSV- und HTML-Dokumentformate und -Ressourcen.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) bietet stark typisierten Zugriff auf relationale Datenbanken durch Objektzuordnung und F# LINQ-Abfragen für diese Datenquellen.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) verfügt über eine Reihe von Typanbietern für die zur Kompilierzeit überprüfte Einbettung von T-SQL in F#.
- [Azure Storage-Typanbieter](https://fsprojects.github.io/AzureStorageTypeProvider/) bietet Typen für Azure Blobs, -Tabellen und -Warteschlangen, sodass Sie auf diese Ressourcen zugreifen können, ohne irgendwo im gesamten Programm Ressourcennamen als Zeichenfolgen angeben zu müssen.
- [FSharp.DataData.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) enthält den **GraphQLProvider-** , der Typen auf Grundlage eines mittels URL angegebenen GraphQL-Servers bereitstellt.

Bei Bedarf können Sie [eigene benutzerdefinierte Typanbieter erstellen](creating-a-type-provider.md) oder auf Typanbieter verweisen, die von anderen Entwicklern erstellt wurden. Angenommen, in einer Organisation wird ein Datendienst verwendet, der eine große und wachsende Anzahl von benannten Datasets bereitstellt, die alle ein eigenes, stabiles Datenschema verwenden. Sie möchten einen Typanbieter erstellen, der die Schemas liest und die neuesten verfügbaren Datasets auf eine stark typisierte Weise für den Programmierer darstellt.

## <a name="see-also"></a>Siehe auch

- [Tutorial: Erstellen eines Typanbieters](creating-a-type-provider.md)
- [F#-Sprachreferenz](../../language-reference/index.md)
