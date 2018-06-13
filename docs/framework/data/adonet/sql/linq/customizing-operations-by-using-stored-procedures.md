---
title: Anpassen von Operationen durch Verwendung von gespeicherten Prozeduren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
ms.openlocfilehash: 1220ea07501e68fd8d2a8075c686d949be9a7020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360208"
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
