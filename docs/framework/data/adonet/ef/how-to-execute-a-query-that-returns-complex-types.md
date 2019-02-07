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
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="19425-102">Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="19425-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="19425-103">Dieses Thema zeigt, wie eine [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfrage ausgeführt wird, die Entitätstypobjekte zurückgibt, die eine Eigenschaft eines komplexen Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="19425-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="19425-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="19425-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="19425-105">Hinzufügen der [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt und Konfigurieren Ihres Projekts zur Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19425-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="19425-106">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="19425-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="19425-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="19425-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="19425-108">Klicken Sie mit der Doppelklicken auf die EDMX-Datei zum Anzeigen des Modells in der [Fenster "Modellbrowser"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) des Entity Designers.</span><span class="sxs-lookup"><span data-stu-id="19425-108">Double click the .edmx file to display the model in the [Model Browser window](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) of the Entity Designer.</span></span> <span data-ttu-id="19425-109">Wählen Sie auf der Entity Designer-Oberfläche, die `Email` und `Phone` Eigenschaften der `Contact` Entitätstyp, und klicken Sie dann mit der rechten Maustaste und wählen **in neuen komplexen Typ Umgestalten**.</span><span class="sxs-lookup"><span data-stu-id="19425-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4.  <span data-ttu-id="19425-110">Ein neuer komplexer Typ mit dem ausgewählten `Email` und `Phone` Eigenschaften wird hinzugefügt, um die **Modellbrowser**.</span><span class="sxs-lookup"><span data-stu-id="19425-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="19425-111">Der komplexe Typ ist ein Standardname zugewiesen: Benennen Sie den Typ `EmailPhone` in die **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="19425-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="19425-112">Außerdem wurde dem Entitätstyp `ComplexProperty` die Eigenschaft `Contact` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="19425-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="19425-113">Geben Sie der Eigenschaft den Namen `EmailPhoneComplexType.`</span><span class="sxs-lookup"><span data-stu-id="19425-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="19425-114">Informationen zum Erstellen und Ändern von komplexen Typen mithilfe des Assistenten für Entity Data Model finden Sie unter [Vorgehensweise: Umgestalten vorhandener Eigenschaften in eine komplexe Typeigenschaft](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) und [Vorgehensweise: Erstellen und Ändern von komplexen Typen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="19425-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) and [How to: Create and Modify Complex Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19425-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19425-115">Example</span></span>  
 <span data-ttu-id="19425-116">Das folgende Beispiel führt eine Abfrage, die eine Auflistung von zurückgibt `Contact` -Objekte und zeigt zwei Eigenschaften des der `Contact` Objekte: `ContactID` und die Werte der `EmailPhoneComplexType` komplexen Typ.</span><span class="sxs-lookup"><span data-stu-id="19425-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
