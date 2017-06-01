---
title: "Versionsbezogene &#196;nderungen in .NET Framework 4.6.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Versionsbezogene &#196;nderungen in .NET Framework 4.6.1
In seltenen Fällen wirken sich Neuausrichtungsänderungen auf Apps aus, die für [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] neu kompiliert wurden. Sofern nicht anderweitig angegeben, wirken sich diese Änderungen nicht auf Binärdateien aus, die eine niedrigere Version von .NET Framework als Ziel haben, jedoch unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden.  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] umfasst Neuausrichtungsänderungen in den folgenden Bereichen:  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="WCF"></a>   
## Windows Communication Foundation  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|--------------|--------------|------------------|------------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> \(<xref:System.IdentityModel.Claims>\-Namespace\)|Wenn in Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, ein X509\-Anspruchssatz über ein Zertifikat mit mehreren DNS\-Einträge im SAN\-Feld initialisiert wird, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A>\-Methode, das `claimType`\-Argument mit allen DNS\-Einträgen abzugleichen.<br /><br /> Bei Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A>\-Methode, das `claimType`\-Argument nur mit den letzten DNS\-Eintrag abzustimmen.|Diese Änderung wirkt sich auf alle Apps aus, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind. Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, sind nicht betroffen.<br /><br /> Für Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, kann dieses Verhalten jedoch deaktiviert werden. Darüber hinaus ist es möglich, dass dieses Verhalten für Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, aber unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden, aktiviert wird. Weitere Informationen finden Sie unter [Problemumgehung: X509CertificiateClaimSet.FindClaims\-Methode](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|Gering|  
  
<a name="WinForms"></a>   
## Windows Forms  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|--------------|--------------|------------------|------------|  
|<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>Methode \(<xref:System.Windows.Forms>\-Namespace\)|In Windows Forms\-Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, kann eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>\-Implementierung Meldungen beim Aufruf der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>\-Methode sicher filtern, wenn die <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>\-Implementierung:<br /><br /> <ul><li>Mindestens eine der folgenden Aktionen ausführt:<br /><br /> <ul><li>Hinzufügen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.AddMessageFilter%2A>\-Methode.</li><li>Entfernen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>\-Methode. \-Methode.</li></ul></li><li>**Und** ruft Nachrichten durch Aufrufen der <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>\-Methode ab.</li></ul><br /> Solche Implementierungen in Windows Forms\-Apps, die auf vorherige Versionen von .NET Framework ausgerichtet sind, lösen in einigen Fällen beim Aufrufen der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>\-Methode eine <xref:System.IndexOutOfRangeException>\-Ausnahme aus.|Diese Änderung wirkt sich auf alle Apps aus, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind. Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, sind nicht betroffen.<br /><br /> Für Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, kann dieses Verhalten jedoch deaktiviert werden. Darüber hinaus ist es möglich, dass dieses Verhalten für Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, aber unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden, aktiviert wird. Weitere Informationen finden Sie unter [Problemumgehung: Benutzerdefinierte IMessageFilter.PreFilterMessage\-Implementierungen](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|Rand|  
  
## Siehe auch  
 [Anwendungskompatibilität in 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)