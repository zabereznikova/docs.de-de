---
title: Typanbieter
description: Erfahren Sie, wie ein f#-Typanbieter für eine Komponente handelt, die Typen, Eigenschaften und Methoden zur Verwendung in Ihren Programmen bereitstellt.
author: cartermp
ms.author: phcart
ms.date: 04/02/2018
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 25697ef6-465e-4248-9de5-1d199d4a8b59
ms.openlocfilehash: 248fb2db2364cdad53e701603fd2cada33498701
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="type-providers"></a>Typanbieter

Ein F#-Typanbieter ist eine Komponente, die Typen, Eigenschaften und Methoden zur Verwendung im Programm bereitstellt. Typanbieter erstellen, so genannten **bereitgestellten Typen**, dem werden vom f#-Compiler generiert und basieren auf einer externen Datenquelle.

Beispielsweise können ein f#-Typanbieter für SQL Typen, die Tabellen und Spalten in einer relationalen Datenbank generieren. In der Tat dies Was ist die [SQLProvider](https://fsprojects.github.io/SQLProvider/) Typanbieter unterstützt.

Vorausgesetzt, dass die Typen von Eingabeparametern für ein Typanbieter abhängig sind. Derartige Eingabe kann einer Beispieldatenquelle (z. B. eine JSON-Schemadatei), eine URL, die direkt an einen externen Dienst oder eine Verbindungszeichenfolge für eine Datenquelle verweist. Ein Typanbieter kann außerdem sicherstellen, dass Gruppen von Typen nur bei Bedarf erweitert werden; Das heißt, werden sie erweitert, wenn die Typen tatsächlich von Ihrer Anwendung verwiesen werden. Dies ermöglicht die direkte, bedarfsabhängige und stark typisierte Integration von umfangreichen Informationsquellen, z. B. Onlinedatenanbietern.

## <a name="generative-and-erased-type-providers"></a>Generierende und gelöschte Typanbietern

Gibt zwei Arten von Typanbietern: generierende und gelöscht.

Generierende Typanbieter erzeugen, Typen, die als .NET-oder Schematypen in der Assembly geschrieben werden können in denen sie erstellt wurden. Dadurch können sie aus Code in anderen Assemblys genutzt werden. Dies bedeutet, dass die typisierte Darstellung der Datenquelle in der Regel eine sein muss, die mit .NET-Typen darstellen möglich ist.

Löschen Typanbieter erzeugen, Typen, die nur genutzt werden können, in der Assembly oder das Projekt, das sie aus generiert werden. Die Typen sind kurzlebige; d. h. werden nicht in eine Assembly geschrieben und können nicht von Code in anderen Assemblys genutzt werden. Sie können enthalten *verzögert* Member, da Sie die bereitgestellten Typen aus einem potenziell unbegrenzte Informationen. Sie eignen sich für eine kleine Teilmenge der eine große und miteinander verbundene Datenquelle verwenden.

## <a name="commonly-used-type-providers"></a>Häufig verwendete Typanbietern

Die folgenden häufig verwendete Bibliotheken enthalten Typanbieter für unterschiedliche Verwendungszwecke:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) enthält Typanbieter für JSON, XML, CSV und HTML-Formaten und Ressourcen dokumentieren.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) stark typisierten Zugriff auf die Relation-Datenbanken über objektzuordnung und f# LINQ-Abfragen für diese Datenquellen bietet.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) hat ein Satz von Typanbieter für den Zeitpunkt der Kompilierung überprüft Einbetten von T-SQL in F# erläutert werden.
- [Azure Storage-Typanbieter](https://fsprojects.github.io/AzureStorageTypeProvider/) stellt Typen bereit, für die Azure-Blobs, Tabellen und Warteschlangen, sodass Sie auf diese Ressourcen zuzugreifen, ohne Ressourcennamen als Zeichenfolgen im gesamten Programm angeben.
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) enthält die **GraphQLProvider**, stellt Typen, die basierend auf einem GraphQL Server durch URL angegeben.

Bei Bedarf können Sie [eine eigene benutzerdefinierte Typanbieter erstellen](creating-a-type-provider.md), oder verweisen Sie Typanbieter, die von anderen Benutzern erstellt wurden. Angenommen, in einer Organisation wird ein Datendienst verwendet, der eine große und wachsende Anzahl von benannten Datasets bereitstellt, die alle ein eigenes, stabiles Datenschema verwenden. Sie möchten einen Typanbieter erstellen, der die Schemas liest und die neuesten verfügbaren Datasets auf eine stark typisierte Weise für den Programmierer darstellt.

## <a name="see-also"></a>Siehe auch
[Lernprogramm: Erstellen eines Typanbieters](creating-a-type-provider.md)

[F#-Sprachreferenz](../../language-reference/index.md)

[Visual F#](../../index.md)
