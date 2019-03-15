---
title: Konfigurieren der Serialisierung in einem Workflowdienst
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 0e0f03a30aa8e8679cf849aa75948e0bc2314fe5
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57843929"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Konfigurieren der Serialisierung in einem Workflowdienst
Workflowdienste sind Windows Communication Foundation (WCF)-Dienste, und daher haben die Möglichkeit, entweder die <xref:System.Runtime.Serialization.DataContractSerializer> (Standard) oder die <xref:System.Xml.Serialization.XmlSerializer>. Beim Schreiben von Nicht-Workflowdiensten wird der Typ des zu verwendenden Serialisierungsprogramms im Dienstvertrag oder Vorgangsvertrag angegeben. Beim Erstellen von WCF-Workflowdienste keinen diese Verträge im Code angeben, aber sie werden vielmehr zur Laufzeit generiert, durch vertragsrückschluss. Weitere Informationen zum vertragsrückschluss finden Sie unter [mithilfe von Verträgen im Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  Das Serialisierungsprogramm wird mithilfe der <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>-Eigenschaft angegeben. Diese kann im Designer festgelegt werden, wie in der folgenden Abbildung dargestellt.  
  
 ![Wenn die SerializerOption-Eigenschaft im Eigenschaftenfenster an.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
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
  
  Bekannte Typen können auch für Workflowdienste angegeben werden. Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](data-contract-known-types.md). Bekannte Typen können im Designer oder im Code angegeben werden. Klicken Sie zum Angeben von bekannter Typen in den Designer auf die Schaltfläche mit den Auslassungspunkten neben der KnownTypes-Eigenschaft in der **Fenster "Eigenschaften"** für eine <xref:System.ServiceModel.Activities.Receive> Aktivität, wie in der folgenden Abbildung dargestellt.   
  
 ![Screenshot des Dialogfelds KnownTypes-Eigenschaft.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Dadurch werden die Typauflistungs-Editor, mit dem Sie suchen, und geben Sie bekannte Typen angezeigt.  
  
 ![Screenshot der Typauflistungs-Editor.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Klicken Sie auf die **neuen Typ hinzufügen** verknüpfen und mithilfe der Dropdownliste wählen oder suchen Sie für einen Typ der Auflistung bekannter Typen hinzu. Verwenden Sie die <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>-Eigenschaft, um bekannte Typen im Code anzugeben, wie im folgenden Beispiel gezeigt.  
  
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
