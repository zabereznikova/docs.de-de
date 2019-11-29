---
title: Typanbieter
description: Erfahren Sie, F# wie ein Typanbieter eine Komponente ist, die Typen, Eigenschaften und Methoden zur Verwendung in ihren Programmen bereitstellt.
ms.date: 04/02/2018
ms.openlocfilehash: 7fa0ff6b5f2b0bc978df2988f22b2042acc22320
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552918"
---
# <a name="type-providers"></a>Typanbieter

Ein F#-Typanbieter ist eine Komponente, die Typen, Eigenschaften und Methoden zur Verwendung im Programm bereitstellt. Typanbieter generieren die als **bereitgestellte Typen bezeichneten Typen**, die vom F# Compiler generiert werden und auf einer externen Datenquelle basieren.

Beispielsweise kann ein F# Typanbieter für SQL Typen generieren, die Tabellen und Spalten in einer relationalen Datenbank darstellen. Tatsächlich ist dies das, was der [SqlProvider](https://fsprojects.github.io/SQLProvider/) -Typanbieter tut.

Die bereitgestellten Typen hängen von den Eingabe Parametern eines Typanbieters ab. Diese Eingabe kann eine Beispiel Datenquelle (z. b. eine JSON-Schema Datei), eine URL, die direkt auf einen externen Dienst verweist, oder eine Verbindungs Zeichenfolge für eine Datenquelle sein. Ein Typanbieter kann außerdem sicherstellen, dass Gruppen von Typen nur Bedarfs gesteuert erweitert werden. Das heißt, Sie werden erweitert, wenn das Programm tatsächlich auf die Typen verweist. Dies ermöglicht die direkte, bedarfsabhängige und stark typisierte Integration von umfangreichen Informationsquellen, z. B. Onlinedatenanbietern.

## <a name="generative-and-erased-type-providers"></a>Generativer und gelöschter Typanbieter

Typanbieter verfügen über zwei Formen: generativ und gelöscht.

Generare Typanbieter erzeugen Typen, die als .NET-Typen in die Assembly geschrieben werden können, in der Sie erstellt werden. Dies ermöglicht die Verwendung von Code in anderen Assemblys. Dies bedeutet, dass die typisierte Darstellung der Datenquelle in der Regel eine solche sein muss, die mit .NET-Typen dargestellt werden kann.

Das Löschen von typanbietern erzeugt Typen, die nur in der Assembly oder im Projekt verwendet werden können, von der Sie generiert werden. Die Typen sind kurzlebig. Das heißt, Sie werden nicht in eine Assembly geschrieben und können nicht von Code in anderen Assemblys verwendet werden. Sie können *verzögerte* Elemente enthalten, sodass Sie die bereitgestellten Typen aus einem potenziell unendlichen Informationsbereich verwenden können. Sie sind nützlich, um eine kleine Teilmenge einer großen und verbundenen Datenquelle zu verwenden.

## <a name="commonly-used-type-providers"></a>Häufig verwendete Typanbieter

Die folgenden häufig verwendeten Bibliotheken enthalten Typanbieter für verschiedene Verwendungen:

- [FSharp. Data](https://fsharp.github.io/FSharp.Data/) umfasst Typanbieter für JSON-, XML-, CSV-und HTML-Dokumentformate und-Ressourcen.
- [SqlProvider](https://fsprojects.github.io/SQLProvider/) bietet mithilfe der Objekt Zuordnung und LINQ- F# Abfragen für diese Datenquellen einen stark typisierten Zugriff auf beziehungsdatenbanken.
- [FSharp. Data. SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) verfügt über einen Satz von typanbietern für die Kompilierzeit-überprüfte F#Einbettung von T-SQL in.
- [Azure Storage Typanbieter](https://fsprojects.github.io/AzureStorageTypeProvider/) bietet Typen für Azure-blobdateien,-Tabellen und-Warteschlangen, sodass Sie auf diese Ressourcen zugreifen können, ohne dass Sie Ressourcennamen im gesamten Programm als Zeichen folgen angeben müssen.
- [FSharp. Data. graphql](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) enthält den **graphqlprovider**, der Typen auf Grundlage eines von URL angegebenen graphql-Servers bereitstellt.

Bei Bedarf können Sie [eigene benutzerdefinierte Typanbieter erstellen](creating-a-type-provider.md)oder auf Typanbieter verweisen, die von anderen Benutzern erstellt wurden. Angenommen, in einer Organisation wird ein Datendienst verwendet, der eine große und wachsende Anzahl von benannten Datasets bereitstellt, die alle ein eigenes, stabiles Datenschema verwenden. Sie möchten einen Typanbieter erstellen, der die Schemas liest und die neuesten verfügbaren Datasets auf eine stark typisierte Weise für den Programmierer darstellt.

## <a name="see-also"></a>Siehe auch

- [Tutorial: Erstellen eines Typanbieters](creating-a-type-provider.md)
- [F#-Sprachreferenz](../../language-reference/index.md)
