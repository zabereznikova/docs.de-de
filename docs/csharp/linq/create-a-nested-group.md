---
title: Erstellen einer geschachtelten Gruppe
description: So erstellen Sie eine geschachtelte Gruppe
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ff2c0c00ab23346cbaa3ba7c36a0cba25e03b89b
ms.lasthandoff: 03/13/2017

---
# <a name="create-a-nested-group"></a>Erstellen einer geschachtelten Gruppe

Im folgenden Beispiel wird veranschaulicht, wie geschachtelte Gruppen in einem LINQ-Abfrageausdruck erstellt werden. Jede Gruppe, die nach Studienjahr oder Klassenstufe erstellt wird, wird basierend auf den Namen der einzelnen Personen weiter in Gruppen unterteilt.  
  
## <a name="example"></a>Beispiel

 > [!NOTE]
 > Dieses Beispiel enthält Verweise auf Objekte, die im Beispielcode in [Abfragen einer Sammlung von Objekten](query-a-collection-of-objects.md) definiert sind. 

 [!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 Beachten Sie, das drei geschachtelte `foreach`-Schleifen für die Iteration über die inneren Elemente einer geschachtelten Gruppe erforderlich sind.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)
