---
title: "Anpassen von Operationen durch ausschließliche Verwendung von gespeicherten Prozeduren"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: eba9e4462c1a71708173994dfb3efaf4199248c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Anpassen von Operationen durch ausschließliche Verwendung von gespeicherten Prozeduren
Der Zugriff auf Daten nur mit gespeicherten Prozeduren ist ein gängiges Szenario.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Sie können das Beispiel in [anpassen Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) nach und Ersetzen Sie auch die erste Abfrage (wodurch dynamische SQL-Ausführung) durch den Aufruf einer Methode, die eine gespeicherte Prozedur dient als Wrapper.  
  
 Gehen Sie wie im folgenden Beispiel von der `CustomersByCity`-Methode aus.  
  
### <a name="code"></a>Code  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Der folgende Code wird ohne jedes dynamische SQL ausgeführt.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch  
 [Aufgaben der Entwickler beim Überschreiben von Standardverhalten](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
