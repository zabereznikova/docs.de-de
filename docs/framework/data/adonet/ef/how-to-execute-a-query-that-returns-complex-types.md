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
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="649ba-102">Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="649ba-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="649ba-103">Dieses Thema zeigt, wie eine [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfrage ausgeführt wird, die Entitätstypobjekte zurückgibt, die eine Eigenschaft eines komplexen Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="649ba-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="649ba-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="649ba-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="649ba-105">Fügen Sie das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt hinzu, und konfigurieren Sie das Projekt für die Verwendung der Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="649ba-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="649ba-106">Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="649ba-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="649ba-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="649ba-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="649ba-108">Doppelklicken Sie auf die EDMX-Datei, um das Modell im [Fenstermodell Browser](/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) der Entity Designer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="649ba-108">Double click the .edmx file to display the model in the [Model Browser window](/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) of the Entity Designer.</span></span> <span data-ttu-id="649ba-109">Wählen Sie auf der Entity Designer-Oberfläche die `Email` `Phone` Eigenschaften und des `Contact` Entitäts Typs aus, klicken Sie dann mit der rechten Maustaste, und wählen Sie **in neuen komplexen Typ Umgestalten**aus.</span><span class="sxs-lookup"><span data-stu-id="649ba-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4. <span data-ttu-id="649ba-110">Ein neuer komplexer Typ mit den ausgewählten `Email` `Phone` Eigenschaften und wird dem **Modell Browser**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="649ba-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="649ba-111">Dem komplexen Typ wird ein Standardname zugewiesen: benennen Sie den Typ `EmailPhone` im **Eigenschaften** Fenster in um.</span><span class="sxs-lookup"><span data-stu-id="649ba-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="649ba-112">Außerdem wurde dem Entitätstyp `ComplexProperty` die Eigenschaft `Contact` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="649ba-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="649ba-113">Geben Sie der Eigenschaft den Namen `EmailPhoneComplexType.`</span><span class="sxs-lookup"><span data-stu-id="649ba-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="649ba-114">Weitere Informationen zum Erstellen und ändern komplexer Typen mithilfe des Entity Data Model-Assistenten finden Sie unter Gewusst [wie: umgestalten vorhandener Eigenschaften in eine Eigenschaft eines komplexen Typs](/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) und Gewusst [wie: Erstellen und ändern komplexer Typen](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="649ba-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) and [How to: Create and Modify Complex Types](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="649ba-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="649ba-115">Example</span></span>  
 <span data-ttu-id="649ba-116">Im folgenden Beispiel wird eine Abfrage ausgeführt, die eine Auflistung von `Contact` -Objekten zurückgibt und zwei Eigenschaften der `Contact` -Objekte anzeigt: `ContactID` und die Werte des `EmailPhoneComplexType` komplexen Typs.</span><span class="sxs-lookup"><span data-stu-id="649ba-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
