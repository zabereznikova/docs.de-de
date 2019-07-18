---
title: Anpassen von Operationen durch ausschließliche Verwendung von gespeicherten Prozeduren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 61230ffc5cd055ee64de9d519cdfb4d76c856ca3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038050"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Anpassen von Operationen durch ausschließliche Verwendung von gespeicherten Prozeduren
Der Zugriff auf Daten nur mit gespeicherten Prozeduren ist ein gängiges Szenario.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Sie können das Beispiel in [anpassen Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) durch, und Ersetzen Sie die erste Abfrage (die Ausführung von dynamischem SQL führt) durch den Aufruf einer Methode, die eine gespeicherte Prozedur umschließt.  
  
 Gehen Sie wie im folgenden Beispiel von der `CustomersByCity`-Methode aus.  
  
### <a name="code"></a>Code  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Der folgende Code wird ohne jedes dynamische SQL ausgeführt.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Aufgaben der Entwickler beim Überschreiben von Standardverhalten](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
