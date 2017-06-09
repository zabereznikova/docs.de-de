---
title: "Geordnete Verarbeitung von Nachrichten im Single-Parallelit&#228;tsmodus | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Geordnete Verarbeitung von Nachrichten im Single-Parallelit&#228;tsmodus
WCF macht keine Zusagen bezüglich der Reihenfolge, in der Nachrichten verarbeitet werden, es sei denn, der zugrunde liegenden Kanal ist sitzungsbasiert. Beispielsweise kann ein WCF\-Dienst, der MsmqInputChannel \(einen nicht sitzungsbasierten Kanal\) verwendet, Nachrichten nicht in der Reihenfolge verarbeiten. Es gibt mehrere Situationen, in denen ein Entwickler die Verarbeitung in der Reihenfolge und keine sitzungsbasierte Verarbeitung wünscht.In diesem Thema wird beschrieben, wie Sie dieses Verhalten konfigurieren, wenn ein Dienst im Single\-Parallelitätsmodus ausgeführt wird.  
  
## Verarbeiten von Nachrichten innerhalb der der normalen Reihenfolge  
 Ein neues Attribut mit dem Namen <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> wurde <xref:System.ServiceModel.ServiceBehaviorAttribute> hinzugefügt.Wenn <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> auf TRUE und <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> auf <xref:System.ServiceModel.ConcurrencyMode> festgelegt ist, werden an den Dienst gesendete Nachrichten in der normalen Reihenfolge verarbeitet.Der folgende Codeausschnitt veranschaulicht, wie diese Attribute festgelegt werden.  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
  
```  
  
 Wenn <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> auf einen anderen Wert festgelegt ist, wird <xref:System.InvalidOperationException> ausgelöst.  
  
## Siehe auch  
 [Sitzungen, Instanziierung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)   
 [Parallelität](../../../../docs/framework/wcf/samples/concurrency.md)