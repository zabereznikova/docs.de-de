---
title: "Gewusst wie: Festlegen der standardm&#228;&#223;igen zeitbasierten Cacherichtlinie f&#252;r eine Anwendung | Microsoft Docs"
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
helpviewer_keywords: 
  - "zeitbasierte Cacherichtlinien"
  - "Cache [.NET Framework], zeitbasierte Richtlinien"
  - "zeitbasierte Standardcacherichtlinie"
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Gewusst wie: Festlegen der standardm&#228;&#223;igen zeitbasierten Cacherichtlinie f&#252;r eine Anwendung
Die zeitgebundenen Cacherichtlinie ermöglicht einer Anwendung, um das Zwischenspeicherungsverhalten sein, das durch die Header definiert werden, die mit der zwischengespeicherten Ressource gesendet werden und das Cacheverhalten verfügen, das in Abschnitten 13 und 14 von RFC 2616 definiert ist, verfügbar an [http:\/\/www.ietf.org](http://www.ietf.org/).  Dies ist das entsprechende Cacheverhalten für die meisten Anwendungen.  
  
### Um die standardmäßige automatische Richtlinie für eine Anwendung festlegen  
  
1.  Erstellen Sie ein Standard zeitbasiertes Richtlinienobjekt.  
  
2.  Legen Sie das Richtlinienobjekt als Standard für die Anwendungsdomäne fest.  
  
## Beispiel  
 Die zwei Beispiele in diesem Abschnitt erzeugen identische Richtlinien.  
  
 Das folgende Beispiel erstellt eine zeitgebundenen Richtlinie und legt ihn als Standard für die Anwendungsdomäne fest.  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 Sie können die zeitgebundenen Cacherichtlinie mithilfe der <xref:System.Net.Cache.RequestCachePolicy>\-Klasse wie im folgenden Beispiel gezeigt auch erstellen:  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
  
```  
  
## Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)   
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)