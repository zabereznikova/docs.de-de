---
title: "Konfigurieren der Serialisierung in einem Workflowdienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Konfigurieren der Serialisierung in einem Workflowdienst
Workflowdienste sind [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste und können daher entweder <xref:System.Runtime.Serialization.DataContractSerializer> \(Standard\) oder <xref:System.Xml.Serialization.XmlSerializer> verwenden.Beim Schreiben von Nicht\-Workflowdiensten wird der Typ des zu verwendenden Serialisierungsprogramms im Dienstvertrag oder Vorgangsvertrag angegeben.Beim Erstellen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Workflowdiensten geben Sie diese Verträge nicht im Code an, sie werden vielmehr zur Laufzeit vom Vertragsrückschluss generiert.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Vertragsrückschluss finden Sie unter [Verwenden von Verträgen im Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).Das Serialisierungsprogramm wird mithilfe der <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>\-Eigenschaft angegeben.Diese kann im Designer festgelegt werden, wie in der folgenden Abbildung dargestellt.  
  
 ![Festlegen des Serialisierungsprogramms](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")  
  
 Das Serialisierungsprogramm kann auch im Code festgelegt werden, wie im folgenden Beispiel gezeigt.  
  
```  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
  
```  
  
 Bekannte Typen können auch für Workflowdienste angegeben werden.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu bekannten Typen finden Sie unter [Bekannte Typen in Datenverträgen](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).Bekannte Typen können im Designer oder im Code angegeben werden.Um bekannte Typen im Designer anzugeben, klicken Sie im Eigenschaftenfenster für eine <xref:System.ServiceModel.Activities.Receive>\-Aktivität neben der KnownTypes\-Eigenschaft auf die Schaltfläche mit den Auslassungspunkten, wie in der folgenden Abbildung gezeigt.  
  
 ![KnownTypes&#45;Eigenschaft](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")  
  
 Dadurch wird der Typauflistungs\-Editor angezeigt, mit dem Sie bekannte Typen suchen und angeben können.  
  
 ![Hinzufügen von bekannten Typen](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")  
  
 Klicken Sie auf den Link **Neuen Typ hinzufügen**, und verwenden Sie die Dropdownliste, um einen Typ zu suchen oder auszuwählen, der der Auflistung bekannter Typen hinzugefügt werden soll.Verwenden Sie die <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>\-Eigenschaft, um bekannte Typen im Code anzugeben, wie im folgenden Beispiel gezeigt.  
  
```  
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
  
 Ein vollständiges Codebeispiel für das Konfigurieren der Serialisierung für einen Workflowdienst finden Sie unter [Formatieren von Meldungen in Workflowdiensten](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md).