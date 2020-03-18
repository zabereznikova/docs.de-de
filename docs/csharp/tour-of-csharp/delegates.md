---
title: C#-Delegaten – Überblick über C#
description: Hier lernen Sie späte Bindungen mit C#-Delegaten kennen.
ms.date: 02/27/2020
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: b1740ddc65dcb0ee8775f4cbaa8356293ea55fae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159168"
---
# <a name="delegates"></a>Delegaten

Ein ***Delegattyp*** stellt Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp dar. Delegate ermöglichen die Behandlung von Methoden als Entitäten, die Variablen zugewiesen und als Parameter übergeben werden können. Delegaten ähneln konzeptionell Funktionszeigern, die es in einigen anderen Sprachen gibt. Im Gegensatz zu Funktionszeigern sind Delegaten objektorientiert und typsicher.

Im folgenden Beispiel wird ein Delegattyp namens `Function` deklariert und verwendet.

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

Eine Instanz des Delegattyps `Function` kann auf jede Methode verweisen, die ein `double`-Argument und einen `double`-Wert akzeptiert. Die `Apply`-Methode wendet eine bestimmte Funktion auf die Elemente eines `double[]` an, wobei ein `double[]` mit den Ergebnissen zurückgegeben wird. In der `Main`-Methode wird `Apply` verwendet, um drei verschiedene Funktionen auf ein `double[]` anzuwenden.

Ein Delegat kann entweder auf eine statische Methode verweisen (z.B. `Square` oder `Math.Sin` im vorherigen Beispiel) oder eine Instanzmethode (z.B. `m.Multiply` im vorherigen Beispiel). Ein Delegat, der auf eine Instanzmethode verweist, verweist auch auf ein bestimmtes Objekt, und wenn die Instanzmethode durch den Delegaten aufgerufen wird, wird das Objekt `this` im Aufruf.

Delegaten können auch mithilfe anonymer Funktionen erstellt werden, bei denen es sich um „Inlinemethoden“ handelt, die bei der Deklaration erstellt werden. Anonyme Funktionen können die lokalen Variablen der umgebenden Methoden sehen. Im folgenden Beispiel wird keine Klasse erstellt:

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

Ein Delegat weiß nicht und interessiert sich nicht dafür, welche Klasse der Methode er referenziert. Wichtig ist nur, dass die referenzierte Methode über dieselben Parameter und denselben Rückgabetyp wie der Delegat verfügt.

>[!div class="step-by-step"]
>[Zurück](interfaces.md)
>[Weiter](attributes.md)
