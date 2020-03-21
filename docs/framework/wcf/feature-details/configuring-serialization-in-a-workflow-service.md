---
title: Konfigurieren der Serialisierung in einem Workflowdienst
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: f894f2e044e35bb278f975ef2385a6b22a8bea49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185335"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="b6b73-102">Konfigurieren der Serialisierung in einem Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="b6b73-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="b6b73-103">Workflowdienste sind Windows Communication Foundation (WCF)-Dienste und <xref:System.Runtime.Serialization.DataContractSerializer> haben daher die <xref:System.Xml.Serialization.XmlSerializer>Möglichkeit, entweder die (Standardeinstellung) oder die zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6b73-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="b6b73-104">Beim Schreiben von Nicht-Workflowdiensten wird der Typ des zu verwendenden Serialisierungsprogramms im Dienstvertrag oder Vorgangsvertrag angegeben.</span><span class="sxs-lookup"><span data-stu-id="b6b73-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="b6b73-105">Beim Erstellen von WCF-Workflowdiensten geben Sie diese Verträge nicht im Code an, sondern werden zur Laufzeit durch Vertragsrückschluss generiert.</span><span class="sxs-lookup"><span data-stu-id="b6b73-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="b6b73-106">Weitere Informationen zu Vertragsrückschluss finden Sie unter [Verwenden von Verträgen im Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b6b73-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="b6b73-107">Das Serialisierungsprogramm wird mithilfe der <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>-Eigenschaft angegeben.</span><span class="sxs-lookup"><span data-stu-id="b6b73-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="b6b73-108">Diese kann im Designer festgelegt werden, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b6b73-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![Festlegen der SerializerOption-Eigenschaft im Eigenschaftenfenster.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="b6b73-110">Das Serialisierungsprogramm kann auch im Code festgelegt werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b6b73-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
  <span data-ttu-id="b6b73-111">Bekannte Typen können auch für Workflowdienste angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b6b73-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="b6b73-112">Weitere Informationen zu bekannten Typen finden Sie unter [Bekannte Typen für Datenvertrags .](data-contract-known-types.md)</span><span class="sxs-lookup"><span data-stu-id="b6b73-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="b6b73-113">Bekannte Typen können im Designer oder im Code angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b6b73-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="b6b73-114">Um bekannte Typen im Designer anzugeben, klicken Sie im Eigenschaftenfenster für eine <xref:System.ServiceModel.Activities.Receive> Aktivität, wie in der folgenden Abbildung dargestellt, auf die Schaltfläche Auslassung neben der Eigenschaft KnownTypes im **Eigenschaftenfenster.**</span><span class="sxs-lookup"><span data-stu-id="b6b73-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>
  
 ![Screenshot des Dialogfelds der KnownTypes-Eigenschaft.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="b6b73-116">Dadurch wird der Typsammlungs-Editor angezeigt, mit dem Sie nach bekannten Typen suchen und diese angeben können.</span><span class="sxs-lookup"><span data-stu-id="b6b73-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![Screenshot des Typsammlungs-Editors.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="b6b73-118">Klicken Sie auf den Link **Neuer Typ hinzufügen,** und verwenden Sie die Dropdownliste, um einen Typ auszuwählen oder zu suchen, der der Sammlung bekannter Typen hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6b73-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="b6b73-119">Verwenden Sie die <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>-Eigenschaft, um bekannte Typen im Code anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b6b73-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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
