---
title: "Vorgehensweise: Erstellen eines grundlegenden Datenvertrags f&#252;r eine Klasse oder Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Datenverträge [WCF], Erstellen für eine Klasse oder Struktur"
  - "DataContractAttribute-Klasse"
  - "DataMemberAttribute"
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Vorgehensweise: Erstellen eines grundlegenden Datenvertrags f&#252;r eine Klasse oder Struktur
In diesem Thema werden die grundlegenden Schritte zum Erstellen eines Datenvertrags mithilfe einer Klasse oder Struktur beschrieben.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Datenverträgen und zu ihrer Verwendung finden Sie unter [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 Ein Lernprogramm, in dem Sie durch die Schritte zur Erstellung eines grundlegenden [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienstes und \-Clients geführt werden, finden Sie unter [Lernprogramm 'Erste Schritte'](../../../../docs/framework/wcf/getting-started-tutorial.md).  Eine funktionierende Beispielanwendung, die aus einem grundlegenden Dienst und einem Client besteht, finden Sie unter [Grundlegender Datenvertrag](../../../../docs/framework/wcf/samples/basic-data-contract.md).  
  
### So erstellen Sie einen grundlegenden Datenvertrag für eine Klasse oder Struktur  
  
1.  Deklarieren Sie, dass der Typ einen Datenvertrag aufweist, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute>\-Attribut auf die Klasse anwenden.  Beachten Sie, dass alle öffentlichen Typen, einschließlich der Typen ohne Attribute, serialisierbar sind.  Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag ab, wenn das <xref:System.Runtime.Serialization.DataContractAttribute>\-Attribut nicht vorhanden ist.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)], siehe [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
2.  Definieren Sie die zu serialisierenden Member \(Eigenschaften, Felder oder Ereignisse\), indem Sie das <xref:System.Runtime.Serialization.DataMemberAttribute>\-Attribut auf die einzelnen Member anwenden.  Diese Member werden als Datenmember bezeichnet.  Standardmäßig sind alle öffentlichen Typen serialisierbar.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)], siehe [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
    > [!NOTE]
    >  Sie können das <xref:System.Runtime.Serialization.DataMemberAttribute>\-Attribut auf private Felder anwenden und so bewirken, dass die Daten für andere verfügbar gemacht werden.  Stellen Sie sicher, dass der Member keine vertraulichen Daten enthält.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen Datenvertrag für den `Person`\-Typ erstellen, indem Sie die Attribute <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Klassen und ihre Member anwenden.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)   
 [Lernprogramm 'Erste Schritte'](../../../../docs/framework/wcf/getting-started-tutorial.md)   
 [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md)