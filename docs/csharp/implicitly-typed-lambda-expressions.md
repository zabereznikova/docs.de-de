---
title: "Implizit typisierte Lambdaausdrücke"
description: "Implizit typisierte Lambdaausdrücke"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c3621f6feb29929d3681b6ed66cc12c5d8018ba1
ms.lasthandoff: 03/13/2017

---

# <a name="implicitly-typed-lambda-expressions"></a>Implizit typisierte Lambdaausdrücke

Ich verwenden `var` nicht, um diese Ausdrucksbaumstruktur zu deklarieren. Sie können keine implizit typisierte Variablendeklaration verwenden, um einen Lambdaausdruck zu deklarieren.
Dadurch entsteht ein zirkuläres logisches Problem für den Compiler. Die Deklaration `var` stellt den Compiler an, den Variablentyp aus dem Ausdruckstyp rechts vom Zuweisungsoperator abzuleiten. Ein Lambdaausdruck hat keinen Kompilierzeittyp, kann aber in jeden beliebigen passenden Delegats- oder Ausdruckstyp konvertiert werden. Wenn Sie einer Variablen eines Delegats- oder Ausdruckstyps einen Lambdaausdruck zuweisen, sagen Sie damit dem Compiler, dass er den Lambdaausdruck, wenn möglich, in einen Ausdruck oder Delegat konvertieren soll, der der Signatur der zugewiesenen Variablen entspricht. Der Compiler muss versuchen zu erreichen, dass das Objekt, das sich rechts von der Zuweisung befindet, mit dem Typen links von der Zuweisung übereinstimmt. 

Die Objekte, die sich jeweils neben dem Compiler befinden, dürfen dem Compiler nicht auftragen, sich das Objekt auf der jeweils anderen Seite des Zuweisungsoperators anzuschauen, um festzustellen, ob der Typ dieses Objekts mit dem jeweils anderen Objekt übereinstimmt.

Sie können Sich in [diesem Artikel](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) darüber informieren, warum die C#-Programmiersprachen dieses Verhalten vorgibt (zum Download als PDF-Datei)



