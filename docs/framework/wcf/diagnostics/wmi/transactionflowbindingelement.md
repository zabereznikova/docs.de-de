---
title: "TransactionFlowBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## Syntax  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## Methoden  
 Von der TransactionFlowBindingElement\-Klasse werden keine Methoden definiert.  
  
## Eigenschaften  
 Die TransactionFlowBindingElement\-Klasse verfügt über die folgenden Eigenschaften:  
  
### IssuedTokens  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die Anforderung für einen ausgegebenen Sicherheitstoken\-Header \(IssuedTokens von WS\-Trust\) an.  
  
### TransactionProtocol  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das vom Dienst für den Transaktionsfluss verwendete Transaktionsprotokoll.  
  
### Transaktionen  
 Datentyp: Boolescher Wert  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die eingehende Transaktion unterstützt wird.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>