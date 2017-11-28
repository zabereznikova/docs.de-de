---
title: Erstellen einer geschachtelten Gruppe
description: So erstellen Sie eine geschachtelte Gruppe
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 232aa46d975d7c338bbc776e3867f2e566601fde
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="create-a-nested-group"></a>Erstellen einer geschachtelten Gruppe

Im folgenden Beispiel wird veranschaulicht, wie geschachtelte Gruppen in einem LINQ-Abfrageausdruck erstellt werden. Jede Gruppe, die nach Studienjahr oder Klassenstufe erstellt wird, wird basierend auf den Namen der einzelnen Personen weiter in Gruppen unterteilt.  
  
## <a name="example"></a>Beispiel

 > [!NOTE]
 > Dieses Beispiel enthält Verweise auf Objekte, die im Beispielcode in [Abfragen einer Sammlung von Objekten](query-a-collection-of-objects.md) definiert sind. 

 [!code-csharp[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 Beachten Sie, das drei geschachtelte `foreach`-Schleifen für die Iteration über die inneren Elemente einer geschachtelten Gruppe erforderlich sind.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)
