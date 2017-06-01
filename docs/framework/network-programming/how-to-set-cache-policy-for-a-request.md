---
title: "Gewusst wie: Festlegen einer Cacherichtlinie f&#252;r eine Anforderung | Microsoft Docs"
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
  - "Anforderung von Cacherichtlinien"
ms.assetid: 39c15e40-586b-4ac9-9cce-146f74b7e545
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Gewusst wie: Festlegen einer Cacherichtlinie f&#252;r eine Anforderung
Im folgenden Beispiel wird das Festlegen einer Cacherichtlinie für eine Anforderung.  Die Beispielseingabe ist ein URI wie http:\/\/www.contoso.com\/.  
  
## Beispiel  
 Im folgenden Codebeispiel wird eine Cacherichtlinie, die die angeforderte können vom Cache verwendet werden, Ressource, wenn er nicht im Cache für mehr als einen Tag war.  Im Beispiel wird eine Meldung angezeigt, die, ob die Ressource aus Cache\-für Beispiel verwendet wurde, `"The response was retrieved from the cache : False."`\- angibt und dann die Ressource anzeigt.  Eine Anforderung kann von jedem Cache zwischen Client und Server erfüllt werden.  
  
```csharp  
using System;  
using System.Net;  
using System.Net.Cache;  
using System.IO;  
  
namespace Examples.System.Net.Cache  
{  
    public class CacheExample  
    {     
        public static void UseCacheForOneDay(Uri resource)  
        {  
            // Create a policy that allows items in the cache  
            // to be used if they have been cached one day or less.  
            HttpRequestCachePolicy requestPolicy =   
                new HttpRequestCachePolicy (HttpCacheAgeControl.MaxAge,  
                TimeSpan.FromDays(1));  
  
            WebRequest request = WebRequest.Create (resource);  
            // Set the policy for this request only.  
            request.CachePolicy = requestPolicy;  
            HttpWebResponse response = (HttpWebResponse)request.GetResponse();  
            // Determine whether the response was retrieved from the cache.  
            Console.WriteLine ("The response was retrieved from the cache : {0}.",  
               response.IsFromCache);  
            Stream s = response.GetResponseStream ();  
            StreamReader reader = new StreamReader (s);  
            // Display the requested resource.  
            Console.WriteLine(reader.ReadToEnd());  
            reader.Close ();  
            s.Close();  
            response.Close();  
        }  
        public static void Main(string[] args)  
        {  
            if (args == null || args.Length != 1)  
            {  
                Console.WriteLine ("You must specify the URI to retrieve.");  
                return;  
            }  
            UseCacheForOneDay (new Uri(args[0]));  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Cache  
Imports System.IO  
Namespace Examples.System.Net.Cache  
    Public Class CacheExample  
        Public Shared Sub UseCacheForOneDay(ByVal resource As Uri)  
            ' Create a policy that allows items in the cache  
            ' to be used if they have been cached one day or less.  
            Dim requestPolicy As New HttpRequestCachePolicy _  
                  (HttpCacheAgeControl.MaxAge, TimeSpan.FromDays(1))  
            Dim request As WebRequest = WebRequest.Create(resource)  
            ' Set the policy for this request only.  
            request.CachePolicy = requestPolicy  
            Dim response As HttpWebResponse = _  
             CType(request.GetResponse(), HttpWebResponse)  
            ' Determine whether the response was retrieved from the cache.  
            Console.WriteLine("The response was retrieved from the cache : {0}.", _  
                response.IsFromCache)  
            Dim s As Stream = response.GetResponseStream()  
            Dim reader As New StreamReader(s)  
            ' Display the requested resource.  
            Console.WriteLine(reader.ReadToEnd())  
            reader.Close()  
            s.Close()  
            response.Close()  
        End Sub  
        Public Shared Sub Main(ByVal args() As String)  
            If args Is Nothing OrElse args.Length <> 1 Then  
                Console.WriteLine("You must specify the URI to retrieve.")  
                Return  
            End If  
            UseCacheForOneDay(New Uri(args(0)))  
        End Sub  
    End Class  
End Namespace  
  
```  
  
## Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)   
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)