---
title: Lokale Methodenaufrufe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: ec288d5ac2f6466860362be82c619c89204e8f31
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781423"
---
# <a name="local-method-calls"></a>Lokale Methodenaufrufe
Ein Aufruf einer lokalen Methode wird innerhalb des Objektmodells ausgeführt. Ein Remotemethodenaufruf wird von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in SQL übersetzt und zur Ausführung an die Datenbank-Engine übergeben. Lokale Methodenaufrufe sind erforderlich, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wenn den Aufruf nicht in SQL übersetzen kann. Andernfalls wird eine <xref:System.InvalidOperationException> ausgelöst.  
  
## <a name="example-1"></a>Beispiel 1  
 Im folgenden Beispiel wird veranschaulicht, wie eine `Order`-Klasse der Tabelle Bestellungen in der Datenbank Northwind zugewiesen wird. Eine lokale Instanzmethode wurde der Klasse hinzugefügt.  
  
 In Abfrage 1 wird der Konstruktor für die `Order`-Klasse lokal ausgeführt. Hat [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in Abfrage 2 versucht, `LocalInstanceMethod()` in SQL zu übersetzen, würde der Versuch fehlschlagen, und eine <xref:System.InvalidOperationException>-Ausnahme würde ausgelöst. Aber da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Aufrufe einer lokalen Methode unterstützt, löst Abfrage 2 keine Ausnahme aus.  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](background-information.md)
