---
title: "Implizit typisierte Lambdaausdrücke"
description: "Erfahren Sie, warum Sie keine implizit typisierte Variablendeklaration verwenden können, um einen Lambdaausdruck zu deklarieren."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 663613af001f9727c48bd48553540305e47a6bab
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="implicitly-typed-lambda-expressions"></a>Implizit typisierte Lambdaausdrücke

Ich verwenden `var` nicht, um diese Ausdrucksbaumstruktur zu deklarieren. Sie können keine implizit typisierte Variablendeklaration verwenden, um einen Lambdaausdruck zu deklarieren.
Dadurch entsteht ein zirkuläres logisches Problem für den Compiler. Die Deklaration `var` stellt den Compiler an, den Variablentyp aus dem Ausdruckstyp rechts vom Zuweisungsoperator abzuleiten. Ein Lambdaausdruck hat keinen Kompilierzeittyp, kann aber in jeden beliebigen passenden Delegats- oder Ausdruckstyp konvertiert werden. Wenn Sie einer Variablen eines Delegats- oder Ausdruckstyps einen Lambdaausdruck zuweisen, sagen Sie damit dem Compiler, dass er den Lambdaausdruck, wenn möglich, in einen Ausdruck oder Delegat konvertieren soll, der der Signatur der zugewiesenen Variablen entspricht. Der Compiler muss versuchen zu erreichen, dass das Objekt, das sich rechts von der Zuweisung befindet, mit dem Typen links von der Zuweisung übereinstimmt. 

Die Objekte, die sich jeweils neben dem Compiler befinden, dürfen dem Compiler nicht auftragen, sich das Objekt auf der jeweils anderen Seite des Zuweisungsoperators anzuschauen, um festzustellen, ob der Typ dieses Objekts mit dem jeweils anderen Objekt übereinstimmt.

Sie können Sich in [diesem Artikel](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) darüber informieren, warum die C#-Programmiersprachen dieses Verhalten vorgibt (zum Download als PDF-Datei)



