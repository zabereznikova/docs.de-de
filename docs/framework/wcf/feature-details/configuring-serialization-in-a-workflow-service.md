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
# <a name="configuring-serialization-in-a-workflow-service"></a>Konfigurieren der Serialisierung in einem Workflowdienst
Workflowdienste sind Windows Communication Foundation (WCF)-Dienste und <xref:System.Runtime.Serialization.DataContractSerializer> haben daher die <xref:System.Xml.Serialization.XmlSerializer>Möglichkeit, entweder die (Standardeinstellung) oder die zu verwenden. Beim Schreiben von Nicht-Workflowdiensten wird der Typ des zu verwendenden Serialisierungsprogramms im Dienstvertrag oder Vorgangsvertrag angegeben. Beim Erstellen von WCF-Workflowdiensten geben Sie diese Verträge nicht im Code an, sondern werden zur Laufzeit durch Vertragsrückschluss generiert. Weitere Informationen zu Vertragsrückschluss finden Sie unter [Verwenden von Verträgen im Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  Das Serialisierungsprogramm wird mithilfe der <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>-Eigenschaft angegeben. Diese kann im Designer festgelegt werden, wie in der folgenden Abbildung dargestellt.  
  
 ![Festlegen der SerializerOption-Eigenschaft im Eigenschaftenfenster.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 Das Serialisierungsprogramm kann auch im Code festgelegt werden, wie im folgenden Beispiel gezeigt.  
  
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
  
  Bekannte Typen können auch für Workflowdienste angegeben werden. Weitere Informationen zu bekannten Typen finden Sie unter [Bekannte Typen für Datenvertrags .](data-contract-known-types.md) Bekannte Typen können im Designer oder im Code angegeben werden. Um bekannte Typen im Designer anzugeben, klicken Sie im Eigenschaftenfenster für eine <xref:System.ServiceModel.Activities.Receive> Aktivität, wie in der folgenden Abbildung dargestellt, auf die Schaltfläche Auslassung neben der Eigenschaft KnownTypes im **Eigenschaftenfenster.**
  
 ![Screenshot des Dialogfelds der KnownTypes-Eigenschaft.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Dadurch wird der Typsammlungs-Editor angezeigt, mit dem Sie nach bekannten Typen suchen und diese angeben können.  
  
 ![Screenshot des Typsammlungs-Editors.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Klicken Sie auf den Link **Neuer Typ hinzufügen,** und verwenden Sie die Dropdownliste, um einen Typ auszuwählen oder zu suchen, der der Sammlung bekannter Typen hinzugefügt werden soll. Verwenden Sie die <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>-Eigenschaft, um bekannte Typen im Code anzugeben, wie im folgenden Beispiel gezeigt.  
  
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
