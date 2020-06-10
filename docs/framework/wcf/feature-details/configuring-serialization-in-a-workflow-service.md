---
title: Konfigurieren der Serialisierung in einem Workflowdienst
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 5076f3d377a656cb96909cf8df01591dc6ab72b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597539"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="9b80e-102">Konfigurieren der Serialisierung in einem Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="9b80e-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="9b80e-103">Workflow Dienste sind Windows Communication Foundation (WCF)-Dienste und können daher entweder <xref:System.Runtime.Serialization.DataContractSerializer> (Standard) oder verwenden <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="9b80e-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="9b80e-104">Beim Schreiben von Nicht-Workflowdiensten wird der Typ des zu verwendenden Serialisierungsprogramms im Dienstvertrag oder Vorgangsvertrag angegeben.</span><span class="sxs-lookup"><span data-stu-id="9b80e-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="9b80e-105">Beim Erstellen von WCF-Workflow Diensten geben Sie diese Verträge nicht im Code an, sondern werden zur Laufzeit durch Vertrags Rückschluss generiert.</span><span class="sxs-lookup"><span data-stu-id="9b80e-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="9b80e-106">Weitere Informationen zum Vertrags Rückschluss finden Sie unter [Verwenden von Verträgen im Workflow](using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9b80e-106">For more information about contract inference, see  [Using Contracts in Workflow](using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="9b80e-107">Das Serialisierungsprogramm wird mithilfe der <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>-Eigenschaft angegeben.</span><span class="sxs-lookup"><span data-stu-id="9b80e-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="9b80e-108">Diese kann im Designer festgelegt werden, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9b80e-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![Festlegen der serializeroption-Eigenschaft im Eigenschaften Fenster.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="9b80e-110">Das Serialisierungsprogramm kann auch im Code festgelegt werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b80e-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
```csharp  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
  <span data-ttu-id="9b80e-111">Bekannte Typen können auch für Workflowdienste angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9b80e-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="9b80e-112">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="9b80e-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="9b80e-113">Bekannte Typen können im Designer oder im Code angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9b80e-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="9b80e-114">Um bekannte Typen im Designer anzugeben, klicken Sie auf die Schaltfläche mit den Auslassungs Punkten neben der KnownTypes-Eigenschaft im **Eigenschaften Fenster** für eine- <xref:System.ServiceModel.Activities.Receive> Aktivität, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9b80e-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>
  
 ![Screenshot der KnownTypes-Eigenschaft (Dialogfeld)](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="9b80e-116">Dadurch wird der Editor für typauflistungen angezeigt, mit dem Sie bekannte Typen suchen und angeben können.</span><span class="sxs-lookup"><span data-stu-id="9b80e-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![Screenshot des typauflistungs-Editors.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="9b80e-118">Klicken Sie auf den Link **neuen Typ hinzufügen** , und wählen Sie mithilfe der Dropdown Liste einen Typ aus, der der Auflistung bekannter Typen hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b80e-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="9b80e-119">Verwenden Sie die <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>-Eigenschaft, um bekannte Typen im Code anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b80e-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
```csharp
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```
