---
title: <behaviorExtensions>
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: 81ce9bb0e55fe4570f8a21187d9df80ea22393fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191418"
---
# <a name="behaviorextensions"></a>\<behaviorExtensions>
Verhaltenserweiterungen ermöglichen es dem Benutzer, benutzerdefinierte Verhaltenselemente zu erstellen. Diese Elemente können neben den standardmäßigen Windows Communication Foundation (WCF)-Verhaltenselementen verwendet werden. Im `behaviorExtensions`-Abschnitt wird das Element so definiert, dass es in der Konfiguration verwendet werden kann. Im Folgenden finden Sie ein Beispiel für eine typische Verhaltenserweiterung.  
  
```xml  
<system.serviceModel>
  <extensions>
    <behaviorExtensions>
      <add name="myBehavior"
           type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,
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
    <channelSecurity cacheCookies="false"
                     detectReplays="false"
                     maxCachedNonces="9"
                     maxClockSkew="00:00:03"
                     maxCookieCachingTime="00:07:24"
                     replayWindow="00:07:22.2190000" />
  </behavior>
</behaviors>
```  
  
## <a name="security"></a>Sicherheit  
 Es wird dringend empfohlen, voll qualifizierte Assemblynamen beim Registrieren von Typen in der `machine.config`-Datei und der `app.config`-Datei anzugeben. Wenn der Typ nicht eindeutig definiert wurde, sucht der Lader vom Typ CLR an folgenden Speicherorten und in folgender Reihenfolge danach:  
  
 Wenn die Assembly des Typs bekannt ist, durchsucht der Lader den Umleitungsspeicherort der Konfigurationsdatei, den GAC, die aktuelle Assembly mit den Konfigurationsinformationen und das Anwendungsbasisverzeichnis. Wenn die Assembly nicht bekannt ist, durchsucht der Lader die aktuelle Assembly, mscorlib und den vom `TypeResolve`-Ereignishandler zurückgegebenen Speicherort. Diese CLR-Suchreihenfolge kann mit Hooks, wie dem Typweiterleitungsmechanismus und dem AppDomain.TypeResolve-Ereignis, geändert werden.  
  
 Ein Angreifer kann die CLR-Suchreihenfolge ausnutzen und nicht autorisierten Code ausführen. Durch die Verwendung vollqualifizierter (starker) Namen wird ein Typ eindeutig identifiziert und die Sicherheit Ihres Systems verbessert.  
  
 Weitere Informationen finden Sie unter [How the Runtime Locates Assemblies](https://go.microsoft.com/fwlink/?LinkId=95336) und <xref:System.AppDomain.TypeResolve>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>
- [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
