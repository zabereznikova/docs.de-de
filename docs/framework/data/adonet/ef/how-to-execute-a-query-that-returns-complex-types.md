---
title: 'Gewusst wie: Ausführen einer Abfrage, die komplexe Typen zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: b999033046eb251400f033314ae7eb197a8f110a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Gewusst wie: Ausführen einer Abfrage, die komplexe Typen zurückgibt
Dieses Thema zeigt, wie eine [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfrage ausgeführt wird, die Entitätstypobjekte zurückgibt, die eine Eigenschaft eines komplexen Typs enthalten.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1.  Hinzufügen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) zu Ihrem Projekt, und konfigurieren Sie das Projekt verwendet die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Weitere Informationen finden Sie unter [wie: Verwenden des Entity Data Model-Assistenten](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Doppelklicken Sie zum Anzeigen des Modells in die EDMX-Datei der [Modellbrowser-Fenster](http://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) des Entity Designers. Wählen Sie auf der Entity Designer-Oberfläche, die `Email` und `Phone` Eigenschaften der `Contact` Entitätstyp, und klicken Sie dann mit der rechten Maustaste und wählen Sie **in neuen komplexen Typ Umgestalten**.  
  
4.  Einen neuen komplexen Typ mit dem ausgewählten `Email` und `Phone` Eigenschaften wird hinzugefügt, um die **Modellbrowser**. Der komplexe Typ wird ein Standardname zugewiesen: Umbenennen des zum Typ `EmailPhone` in der **Eigenschaften** Fenster. Außerdem wurde dem Entitätstyp `ComplexProperty` die Eigenschaft `Contact` hinzugefügt. Geben Sie der Eigenschaft den Namen `EmailPhoneComplexType.`  
  
     Informationen zum Erstellen und Ändern von komplexen Typen mithilfe des Entity Data Model-Assistenten finden Sie unter [wie: Umgestalten vorhandener Eigenschaften in eine komplexe Typeigenschaft](http://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) und [Vorgehensweise: Erstellen und komplexe Typen ändern](http://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel führt eine Abfrage, die eine Auflistung von zurückgibt `Contact` Objekten und zeigt zwei Eigenschaften des der `Contact` Objekte: `ContactID` und die Werte für die `EmailPhoneComplexType` komplexen Typ.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
