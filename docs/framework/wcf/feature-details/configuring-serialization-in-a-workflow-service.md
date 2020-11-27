---
title: Konfigurieren der Serialisierung in einem Workflowdienst
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: d1cda33c8a469b4a54b6d282b99c07b23e91543e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96284198"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Konfigurieren der Serialisierung in einem Workflowdienst

Workflow Dienste sind Windows Communication Foundation (WCF)-Dienste und können daher entweder <xref:System.Runtime.Serialization.DataContractSerializer> (Standard) oder verwenden <xref:System.Xml.Serialization.XmlSerializer> . Beim Schreiben von Nicht-Workflowdiensten wird der Typ des zu verwendenden Serialisierungsprogramms im Dienstvertrag oder Vorgangsvertrag angegeben. Beim Erstellen von WCF-Workflow Diensten geben Sie diese Verträge nicht im Code an, sondern werden zur Laufzeit durch Vertrags Rückschluss generiert. Weitere Informationen zum Vertrags Rückschluss finden Sie unter  [Verwenden von Verträgen im Workflow](using-contracts-in-workflow.md).  Das Serialisierungsprogramm wird mithilfe der <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>-Eigenschaft angegeben. Diese kann im Designer festgelegt werden, wie in der folgenden Abbildung dargestellt.  
  
 ![Festlegen der serializeroption-Eigenschaft im Eigenschaften Fenster.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
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
  
  Bekannte Typen können auch für Workflowdienste angegeben werden. Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](data-contract-known-types.md). Bekannte Typen können im Designer oder im Code angegeben werden. Um bekannte Typen im Designer anzugeben, klicken Sie auf die Schaltfläche mit den Auslassungs Punkten neben der KnownTypes-Eigenschaft im **Eigenschaften Fenster** für eine- <xref:System.ServiceModel.Activities.Receive> Aktivität, wie in der folgenden Abbildung dargestellt.
  
 ![Screenshot der KnownTypes-Eigenschaft (Dialogfeld)](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Dadurch wird der Editor für typauflistungen angezeigt, mit dem Sie bekannte Typen suchen und angeben können.  
  
 ![Screenshot des typauflistungs-Editors.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Klicken Sie auf den Link **neuen Typ hinzufügen** , und wählen Sie mithilfe der Dropdown Liste einen Typ aus, der der Auflistung bekannter Typen hinzugefügt werden soll. Verwenden Sie die <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>-Eigenschaft, um bekannte Typen im Code anzugeben, wie im folgenden Beispiel gezeigt.  
  
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
