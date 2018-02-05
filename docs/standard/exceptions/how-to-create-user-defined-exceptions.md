---
title: 'Gewusst wie: Erstellen benutzerdefinierter Ausnahmen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c55489a4c0b86142fcda99c5962c896b73691cd6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-user-defined-exceptions"></a>Erstellen benutzerdefinierter Ausnahmen

.NET stellt eine Hierarchie aus Ausnahmeklassen bereit, die letztendlich von der <xref:System.Exception>-Basisklasse abgeleitet werden. Wenn keine der vordefinierten Ausnahmen Ihre Anforderungen erfüllt, können Sie durch Ableiten von der <xref:System.Exception>-Klasse eigene Ausnahmeklassen erstellen.

Beim Erstellen eigener Ausnahmen muss der Klassenname der benutzerdefinierten Ausnahme auf das Wort „Exception“ enden. Implementieren Sie außerdem die drei allgemeinen Konstruktoren, wie im folgenden Beispiel gezeigt. Das Beispiel definiert eine neue Ausnahmeklasse namens `EmployeeListNotFoundException`. Die Klasse wird von <xref:System.Exception> abgeleitet und enthält drei Konstruktoren.

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> In Situationen, in denen Sie Remoting verwenden, müssen Sie sicherstellen, dass die Metadaten für alle benutzerdefinierten Ausnahmen sowohl auf dem Server (Aufgerufener) als auch für den Client (Proxyobjekt oder Aufrufer) verfügbar sind. Weitere Informationen finden Sie unter [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md).

## <a name="see-also"></a>Siehe auch  
[Ausnahmen](index.md)
