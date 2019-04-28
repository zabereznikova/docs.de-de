---
title: Konfigurieren der Serialisierung in einem Workflowdienst
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 0e0f03a30aa8e8679cf849aa75948e0bc2314fe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857484"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="f38a1-102">Konfigurieren der Serialisierung in einem Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="f38a1-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="f38a1-103">Workflowdienste sind Windows Communication Foundation (WCF)-Dienste, und daher haben die Möglichkeit, entweder die <xref:System.Runtime.Serialization.DataContractSerializer> (Standard) oder die <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f38a1-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="f38a1-104">Beim Schreiben von Nicht-Workflowdiensten wird der Typ des zu verwendenden Serialisierungsprogramms im Dienstvertrag oder Vorgangsvertrag angegeben.</span><span class="sxs-lookup"><span data-stu-id="f38a1-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="f38a1-105">Beim Erstellen von WCF-Workflowdienste keinen diese Verträge im Code angeben, aber sie werden vielmehr zur Laufzeit generiert, durch vertragsrückschluss.</span><span class="sxs-lookup"><span data-stu-id="f38a1-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="f38a1-106">Weitere Informationen zum vertragsrückschluss finden Sie unter [mithilfe von Verträgen im Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f38a1-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="f38a1-107">Das Serialisierungsprogramm wird mithilfe der <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>-Eigenschaft angegeben.</span><span class="sxs-lookup"><span data-stu-id="f38a1-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="f38a1-108">Diese kann im Designer festgelegt werden, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f38a1-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![Wenn die SerializerOption-Eigenschaft im Eigenschaftenfenster an.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="f38a1-110">Das Serialisierungsprogramm kann auch im Code festgelegt werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f38a1-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
  <span data-ttu-id="f38a1-111">Bekannte Typen können auch für Workflowdienste angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f38a1-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="f38a1-112">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="f38a1-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="f38a1-113">Bekannte Typen können im Designer oder im Code angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f38a1-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="f38a1-114">Klicken Sie zum Angeben von bekannter Typen in den Designer auf die Schaltfläche mit den Auslassungspunkten neben der KnownTypes-Eigenschaft in der **Fenster "Eigenschaften"** für eine <xref:System.ServiceModel.Activities.Receive> Aktivität, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f38a1-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>   
  
 ![Screenshot des Dialogfelds KnownTypes-Eigenschaft.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="f38a1-116">Dadurch werden die Typauflistungs-Editor, mit dem Sie suchen, und geben Sie bekannte Typen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f38a1-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![Screenshot der Typauflistungs-Editor.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="f38a1-118">Klicken Sie auf die **neuen Typ hinzufügen** verknüpfen und mithilfe der Dropdownliste wählen oder suchen Sie für einen Typ der Auflistung bekannter Typen hinzu.</span><span class="sxs-lookup"><span data-stu-id="f38a1-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="f38a1-119">Verwenden Sie die <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>-Eigenschaft, um bekannte Typen im Code anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f38a1-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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
