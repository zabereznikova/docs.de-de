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
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="aedc1-102">Gewusst wie: Ausführen einer Abfrage, die komplexe Typen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="aedc1-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="aedc1-103">Dieses Thema zeigt, wie eine [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfrage ausgeführt wird, die Entitätstypobjekte zurückgibt, die eine Eigenschaft eines komplexen Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="aedc1-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="aedc1-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="aedc1-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="aedc1-105">Hinzufügen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) zu Ihrem Projekt, und konfigurieren Sie das Projekt verwendet die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aedc1-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="aedc1-106">Weitere Informationen finden Sie unter [wie: Verwenden des Entity Data Model-Assistenten](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="aedc1-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="aedc1-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="aedc1-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="aedc1-108">Doppelklicken Sie zum Anzeigen des Modells in die EDMX-Datei der [Modellbrowser-Fenster](http://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) des Entity Designers.</span><span class="sxs-lookup"><span data-stu-id="aedc1-108">Double click the .edmx file to display the model in the [Model Browser window](http://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) of the Entity Designer.</span></span> <span data-ttu-id="aedc1-109">Wählen Sie auf der Entity Designer-Oberfläche, die `Email` und `Phone` Eigenschaften der `Contact` Entitätstyp, und klicken Sie dann mit der rechten Maustaste und wählen Sie **in neuen komplexen Typ Umgestalten**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4.  <span data-ttu-id="aedc1-110">Einen neuen komplexen Typ mit dem ausgewählten `Email` und `Phone` Eigenschaften wird hinzugefügt, um die **Modellbrowser**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="aedc1-111">Der komplexe Typ wird ein Standardname zugewiesen: Umbenennen des zum Typ `EmailPhone` in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="aedc1-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="aedc1-112">Außerdem wurde dem Entitätstyp `ComplexProperty` die Eigenschaft `Contact` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="aedc1-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="aedc1-113">Geben Sie der Eigenschaft den Namen `EmailPhoneComplexType.`</span><span class="sxs-lookup"><span data-stu-id="aedc1-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="aedc1-114">Informationen zum Erstellen und Ändern von komplexen Typen mithilfe des Entity Data Model-Assistenten finden Sie unter [wie: Umgestalten vorhandener Eigenschaften in eine komplexe Typeigenschaft](http://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) und [Vorgehensweise: Erstellen und komplexe Typen ändern](http://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).</span><span class="sxs-lookup"><span data-stu-id="aedc1-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](http://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) and [How to: Create and Modify Complex Types](http://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aedc1-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aedc1-115">Example</span></span>  
 <span data-ttu-id="aedc1-116">Das folgende Beispiel führt eine Abfrage, die eine Auflistung von zurückgibt `Contact` Objekten und zeigt zwei Eigenschaften des der `Contact` Objekte: `ContactID` und die Werte für die `EmailPhoneComplexType` komplexen Typ.</span><span class="sxs-lookup"><span data-stu-id="aedc1-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
