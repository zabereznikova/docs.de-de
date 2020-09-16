---
title: 'Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 01958637cedcd6d502d51e9f0821ff3a9faae840
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545323"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt
Dieses Thema zeigt, wie eine [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfrage ausgeführt wird, die Entitätstypobjekte zurückgibt, die eine Eigenschaft eines komplexen Typs enthalten.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1. Fügen Sie das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt hinzu, und konfigurieren Sie das Projekt für die Verwendung der Entity Framework. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2. Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. Doppelklicken Sie auf die EDMX-Datei, um das Modell im [Fenstermodell Browser](/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) der Entity Designer anzuzeigen. Wählen Sie auf der Entity Designer-Oberfläche die `Email` `Phone` Eigenschaften und des `Contact` Entitäts Typs aus, klicken Sie dann mit der rechten Maustaste, und wählen Sie **in neuen komplexen Typ Umgestalten**aus.  
  
4. Ein neuer komplexer Typ mit den ausgewählten `Email` `Phone` Eigenschaften und wird dem **Modell Browser**hinzugefügt. Dem komplexen Typ wird ein Standardname zugewiesen: benennen Sie den Typ `EmailPhone` im **Eigenschaften** Fenster in um. Außerdem wurde dem Entitätstyp `ComplexProperty` die Eigenschaft `Contact` hinzugefügt. Geben Sie der Eigenschaft den Namen `EmailPhoneComplexType.`  
  
     Weitere Informationen zum Erstellen und ändern komplexer Typen mithilfe des Entity Data Model-Assistenten finden Sie unter Gewusst [wie: umgestalten vorhandener Eigenschaften in eine Eigenschaft eines komplexen Typs](/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) und Gewusst [wie: Erstellen und ändern komplexer Typen](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Abfrage ausgeführt, die eine Auflistung von `Contact` -Objekten zurückgibt und zwei Eigenschaften der `Contact` -Objekte anzeigt: `ContactID` und die Werte des `EmailPhoneComplexType` komplexen Typs.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
