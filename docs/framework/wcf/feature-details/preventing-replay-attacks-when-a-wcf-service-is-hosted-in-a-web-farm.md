---
title: "Verhindern von Replay-Angriffen bei Hosten eines WCF-Diensts in einer Webfarm | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Verhindern von Replay-Angriffen bei Hosten eines WCF-Diensts in einer Webfarm
Bei Verwendung der Nachrichtensicherheit verhindert WCF\-Angriffe, indem NONCE aus der eingehenden Nachricht heraus erstellt und der `InMemoryNonceCache` daraufhin überprüft wird, ob NONCE enthalten ist.Wenn dies der Fall ist, wird die Nachricht als "Replay" verworfen.Wenn ein WCF\-Dienst in einer Webfarm gehostet wird, da `InMemoryNonceCache` nicht über die Knoten in der Webfarm freigegeben ist, ist der Dienst für Replay\-Angriffe anfällig.Um dieses Szenario zu abzuschwächen, bietet \+WCF 4.5 einen Erweiterungspunkt der es Ihnen ermöglicht, Ihren eigenen freigegebenen NONCE\-Cache zu implementieren, indem eine Klasse von der abstrakten Klasse <xref:System.ServiceModel.Security.NoneCache> abgeleitet wird.  
  
## NoneCache\-Implementierung  
 Um einen eigenen freigegebenen NONCE\-Cache zu implementieren, leiten Sie eine Klasse von <xref:System.ServiceModel.Security.NoneCache> ab, und überschreiben Sie die Methoden [M:System.ServiceModel.Security.NoneCache.CheckNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.CheckNonce%2A> und  [M:System.ServiceModel.Security.NoneCache.TryAddNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.TryAddNonce%2A>.[M:System.ServiceModel.Security.NoneCache.CheckNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.CheckNonce%2A> überprüft, ob das angegebene NONCE im Cache vorhanden ist.[M:System.ServiceModel.Security.NoneCache.TryAddNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.TryAddNonce%2A> versucht, dem Cache NONCE hinzuzufügen.Sobald die Klasse implementiert wurde, verknüpfen Sie sie, indem Sie eine Instanz instanziieren und sie <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSecuritySettings.NonceCache%2A> für die clientseitige Replay\-Erkennung und  <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSecuritySettings.NonceCache%2A> für die serverseitige Replay\-Erkennung zuweisen.Standardmäßig ist keine Konfigurationsunterstützung für diese Funktion verfügbar.  
  
## Siehe auch  
 [Nachrichtensicherheit](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)   
 [SymmetricSecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)