---
title: Anpassen von Operationen durch Verwendung von gespeicherten Prozeduren
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 5d47089092de80488fbae107da630352cb38c1d9
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-operations-by-using-stored-procedures"></a>Anpassen von Operationen durch Verwendung von gespeicherten Prozeduren
Gespeicherte Prozeduren stellen einen allgemeinen Ansatz zum Überschreiben des Standardverhaltens dar. Die Beispiele in diesem Absatz zeigen, wie Sie erzeugte Methoden für gespeicherte Prozeduren verwenden und wie Sie gespeicherte Prozeduren direkt aufrufen können.  
  
 Wenn Sie Visual Studio verwenden, können Sie mithilfe der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Zuweisen von gespeicherten Prozeduren zum Ausführen von einfügungen, Updates und löschungen.  
  
> [!NOTE]
>  Um datenbankgenerierte Werte einzulesen, verwenden Sie Ausgabeparameter in den gespeicherten Prozeduren. Wenn Sie keine Ausgabeparameter verwenden können, schreiben Sie eine partielle Methodenimplementierung, anstatt sich auf den von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] erzeugten Code zu verlassen. Member, die datenbankgenerierten Werten zugeordnet sind, müssen auf die entsprechenden Werte festgelegt werden, nach dem die `INSERT`-Operation oder die `UPDATE`-Operation erfolgreich abgeschlossen wurde. Weitere Informationen finden Sie unter [Aufgaben der Entwickler beim Überschreiben von Standardverhalten](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Nehmen Sie im folgenden Beispiel an, dass die `Northwind`-Klasse zwei Methoden zum Aufruf gespeicherter Prozeduren enthält, die für Überschreibungen in einer abgeleiteten Klasse verwendet werden.  
  
### <a name="code"></a>Code  
 [!code-csharp[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#1)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Die folgende Klasse verwendet diese Methoden für die Überschreibung.  
  
### <a name="code"></a>Code  
 [!code-csharp[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#2)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Sie können `NorthwindThroughSprocs` genau so wie `Northwnd` verwenden.  
  
### <a name="code"></a>Code  
 [!code-csharp[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Aufgaben der Entwickler beim Überschreiben von Standardverhalten](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
