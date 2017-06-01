---
title: "Datenmember-Reihenfolge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Datenverträge [WCF], Sortieren von Membern"
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Datenmember-Reihenfolge
Bei einigen Anwendungen ist es hilfreich, die Reihenfolge zu kennen, in der die Daten aus verschiedenen Datenmembern gesendet oder erwartet werden \(wie z. B. die Reihenfolge, in der die Daten im serialisierten XML angezeigt werden\).Manchmal kann es auch notwendig sein, diese Reihenfolge zu ändern.In diesem Thema werden die Sortierungsregeln beschrieben.  
  
## Grundregeln  
 Zu den grundlegenden Regeln für die Sortierung von Daten gehören u. a.:  
  
-   Wenn ein Datenvertragstyp Teil einer Vererbungshierarchie ist, stehen die Datenmember der Basistypen immer am Anfang der Reihenfolge.  
  
-   Danach folgen die Datenmember des aktuellen Typs, für die die <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>\-Eigenschaft des Attributs <xref:System.Runtime.Serialization.DataMemberAttribute> nicht festgelegt ist, in alphabetischer Reihenfolge.  
  
-   Dann folgen die Datenmember mit der <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>\-Eigenschaft der <xref:System.Runtime.Serialization.DataMemberAttribute>Attributgruppe.Diese sind zunächst nach dem Wert der `Order`\-Eigenschaft geordnet und dann alphabetisch, falls mehr als ein Member eines bestimmten `Order`\-Werts vorhanden ist.Die Reihenfolgenwerte können übersprungen werden.  
  
 Die alphabetische Reihenfolge wird erstellt, indem die <xref:System.String.CompareOrdinal%2A>\-Methode aufgerufen wird.  
  
## Beispiele  
 Betrachten Sie folgenden Code.  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 Das generierte XML sieht ähnlich aus wie das folgende.  
  
```  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>   
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>   
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>   
</DerivedType>  
```  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 [Datenvertragsäquivalenz](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)   
 [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)