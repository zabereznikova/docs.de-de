---
title: "Gewusst wie: Aktivieren von WebRequest zur Verwendung eines Proxys f&#252;r die Internetkommunikation | Microsoft Docs"
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
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Gewusst wie: Aktivieren von WebRequest zur Verwendung eines Proxys f&#252;r die Internetkommunikation
Dieses Beispiel erstellt eine globale Proxyinstanz, die jedes <xref:System.Net.WebRequest> ermöglicht, einen Proxy verwendet, um mit dem Internet zu kommunizieren.  Im Beispiel wird davon ausgegangen, dass der Proxyserver `webproxy` namens und dass auf Port 80 kommuniziert, der Port des standardmäßigen HTTP\-Handler an.  
  
## Beispiel  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Verweise auf **System.Net**\-Namespace.  
  
## Siehe auch  
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)