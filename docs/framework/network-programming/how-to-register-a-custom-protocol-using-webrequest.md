---
title: "Gewusst wie: Registrieren eines benutzerdefinierten Protokolls mit WebRequest | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Gewusst wie: Registrieren eines benutzerdefinierten Protokolls mit WebRequest
Dieses Beispiel zeigt, wie ein bestimmtes Protokoll classthat  wird an anderer Stelle definiert registriert.  In diesem Beispiel ist `CustomWebRequestCreator` das Benutzer\-implementierte Objekt, das die **Create**\-Methode implementiert, die das `CustomWebRequest`\-Objekt zurückgibt.  Im Codebeispiel wird davon ausgegangen, dass Sie den `CustomWebRequest` Code geschrieben haben, der das benutzerdefinierte Protokoll implementiert.  
  
## Beispiel  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
 Verweise auf <xref:System.Net>\-Namespace.  
  
## Siehe auch  
 [Programmieren austauschbarer Protokolle](../../../docs/framework/network-programming/programming-pluggable-protocols.md)