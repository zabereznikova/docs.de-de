---
title: 'Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 6c063c9ef6bfde868c773d941ba2107dbaa9ee73
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827122"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt
Dieses Thema zeigt, wie eine [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfrage ausgeführt wird, die Entitätstypobjekte zurückgibt, die eine Eigenschaft eines komplexen Typs enthalten.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1.  Hinzufügen der [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt und Konfigurieren Ihres Projekts zur Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Klicken Sie mit der Doppelklicken auf die EDMX-Datei zum Anzeigen des Modells in der [Fenster "Modellbrowser"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) des Entity Designers. Wählen Sie auf der Entity Designer-Oberfläche, die `Email` und `Phone` Eigenschaften der `Contact` Entitätstyp, und klicken Sie dann mit der rechten Maustaste und wählen **in neuen komplexen Typ Umgestalten**.  
  
4.  Ein neuer komplexer Typ mit dem ausgewählten `Email` und `Phone` Eigenschaften wird hinzugefügt, um die **Modellbrowser**. Der komplexe Typ ist ein Standardname zugewiesen: Benennen Sie den Typ `EmailPhone` in die **Eigenschaften** Fenster. Außerdem wurde dem Entitätstyp `ComplexProperty` die Eigenschaft `Contact` hinzugefügt. Geben Sie der Eigenschaft den Namen `EmailPhoneComplexType.`  
  
     Informationen zum Erstellen und Ändern von komplexen Typen mithilfe des Assistenten für Entity Data Model finden Sie unter [Vorgehensweise: Umgestalten vorhandener Eigenschaften in eine komplexe Typeigenschaft](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) und [Vorgehensweise: Erstellen und Ändern von komplexen Typen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel führt eine Abfrage, die eine Auflistung von zurückgibt `Contact` -Objekte und zeigt zwei Eigenschaften des der `Contact` Objekte: `ContactID` und die Werte der `EmailPhoneComplexType` komplexen Typ.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
