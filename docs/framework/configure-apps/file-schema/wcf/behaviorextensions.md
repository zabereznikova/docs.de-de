---
title: '&lt;behaviorExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed7c75fb7070b43b850a8f5b812abf0a52c3c16f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorextensionsgt"></a>&lt;behaviorExtensions&gt;
Verhaltenserweiterungen ermöglichen es dem Benutzer, benutzerdefinierte Verhaltenselemente zu erstellen. Diese Elemente können neben den standardmäßigen Windows Communication Foundation (WCF)-Verhaltenselementen verwendet werden. Im `behaviorExtensions`-Abschnitt wird das Element so definiert, dass es in der Konfiguration verwendet werden kann. Im Folgenden finden Sie ein Beispiel für eine typische Verhaltenserweiterung.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="myBehavior" type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
       </behaviorExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 Um dem Element Konfigurationsfunktionen hinzuzufügen, müssen Sie ein Konfigurationselement schreiben und registrieren. Weitere Informationen dazu finden Sie in der <xref:System.Configuration>-Dokumentation.  
  
 Nachdem das Element und sein Konfigurationstyp definiert wurden, kann die Erweiterung wie im folgenden Beispiel verwendet werden.  
  
```xml  
<behaviors>  
    <behavior configurationName="testChannelBehavior">  
        <myBehavior />  
        <channelSecurity cacheCookies="false" detectReplays="false" maxCachedNonces="9"  
            maxClockSkew="00:00:03" maxCookieCachingTime="00:07:24" replayWindow="00:07:22.2190000" />  
    </behavior>  
</behaviors>  
```  
  
## <a name="security"></a>Sicherheit  
 Es wird dringend empfohlen, voll qualifizierte Assemblynamen beim Registrieren von Typen in der `machine.config`-Datei und der `app.config`-Datei anzugeben. Wenn der Typ nicht eindeutig definiert wurde, sucht der Lader vom Typ CLR an folgenden Speicherorten und in folgender Reihenfolge danach:  
  
 Wenn die Assembly des Typs bekannt ist, durchsucht der Lader den Umleitungsspeicherort der Konfigurationsdatei, den GAC, die aktuelle Assembly mit den Konfigurationsinformationen und das Anwendungsbasisverzeichnis. Wenn die Assembly nicht bekannt ist, durchsucht der Lader die aktuelle Assembly, mscorlib und den vom `TypeResolve`-Ereignishandler zurückgegebenen Speicherort. Diese CLR-Suchreihenfolge kann mit Hooks, wie dem Typweiterleitungsmechanismus und dem AppDomain.TypeResolve-Ereignis, geändert werden.  
  
 Ein Angreifer kann die CLR-Suchreihenfolge ausnutzen und nicht autorisierten Code ausführen. Durch die Verwendung vollqualifizierter (starker) Namen wird ein Typ eindeutig identifiziert und die Sicherheit Ihres Systems verbessert.  
  
 Weitere Informationen finden Sie unter [so sucht Common Language Runtime nach Assemblys](http://go.microsoft.com/fwlink/?LinkId=95336) und <xref:System.AppDomain.TypeResolve>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>  
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
