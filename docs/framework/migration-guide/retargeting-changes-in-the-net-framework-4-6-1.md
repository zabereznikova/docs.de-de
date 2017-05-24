---
title: "Änderungen der Neuzuweisungen in .NET Framework 4.6.1 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0adc4a6cae566b6a15c5fa492620abb74b47335b
ms.contentlocale: de-de
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-461"></a>Versionsbezogene Änderungen in .NET Framework 4.6.1
In seltenen Fällen wirken sich Neuausrichtungsänderungen auf Apps aus, die für [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] neu kompiliert wurden. Sofern nicht anderweitig angegeben, wirken sich diese Änderungen nicht auf Binärdateien aus, die eine niedrigere Version von .NET Framework als Ziel haben, jedoch unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden.  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] umfasst Neuausrichtungsänderungen in den folgenden Bereichen:  
  
-   [Kernspeicher](#Core)  
  
-   [Codeverträge](#Contracts)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="Core"></a>   
## <a name="core"></a>Kernspeicher  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>|Für Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und höhere Versionen ausgerichtet sind, wurde das Pfadtrennzeichen in der <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A>-Eigenschaft von <xref:System.IO.Compression.ZipArchiveEntry>-Objekten, die durch Überladungen der <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>-Methode erstellt wurden, von einem umgekehrten Schrägstrich „\\“) in einen normalen Schrägstrich („/“) geändert.|Die Änderung bringt die .NET-Implementierung in Einklang mit Abschnitt 4.4.17.1 der [ZIP-Dateiformatspezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) und ermöglicht es, dass ZIP-Archive auf Nicht-Windows-Systemen entpackt werden.<br /><br /> Für Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und höhere Versionen ausgerichtet sind, kann dieses Verhalten jedoch deaktiviert werden. Weitere Informationen finden Sie unter [Entschärfung: Pfadtrennzeichen für ZipArchiveEntry.FullName](../../../docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|Kante|  
  
<a name="Contracts"></a>   
## <a name="code-contracts"></a>Codeverträge  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=fullName> und <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=fullName> sowie Aufrufe von <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName>|Für Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, gibt der Rewriter die Compilerwarnung CC1036 aus: „Aufruf der Methode 'System.String.IsNullOrWhiteSpace(System.String)' ohne [Pure] in der Methode erkannt...“|Dies ist eher eine Compilerwarnung als ein Compilerfehler.<br /><br /> Dieses Verhalten wurde in [GitHub-Problem Nr. 339](https://github.com/Microsoft/CodeContracts/issues/339) behandelt. Um diese Warnung zu vermeiden, können Sie eine aktualisierte Version des Quellcodes für die Codevertragstools von [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md) herunterladen und kompilieren. Informationen zum Herunterladen befinden sich am unteren Rand der Seite.|Nebenversion|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation"></a>Windows Communication Foundation  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> (<xref:System.IdentityModel.Claims>-Namespace)|Wenn in Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, ein X509-Anspruchssatz über ein Zertifikat mit mehreren DNS-Einträge im SAN-Feld initialisiert wird, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A>-Methode, das `claimType`-Argument mit allen DNS-Einträgen abzugleichen.<br /><br /> Für Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A>-Methode, das `claimType`-Argument nur mit dem letzten DNS-Eintrag zu vergleichen.|Diese Änderung wirkt sich auf alle Apps aus, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind. Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, sind nicht betroffen.<br /><br /> Für Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, kann dieses Verhalten jedoch deaktiviert werden. Darüber hinaus ist es möglich, dass dieses Verhalten für Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, aber unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden, aktiviert wird. Weitere Informationen finden Sie unter [Entschärfung: X509CertificateClaimSet.FindClaims-Methode](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|Nebenversion|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>-Methode (<xref:System.Windows.Forms>-Namespace)|In Windows Forms-Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, kann eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>-Implementierung Nachrichten sicher filtern, wenn die <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>-Methode aufgerufen wird, falls Folgendes für die <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>-Implementierung gilt:<br /><br /> <ul><li>Mindestens eine der folgenden Aktionen ausführt:<br /><br /> <ul><li>Fügt einen Nachrichtenfilter durch Aufrufen der Methode <xref:System.Windows.Forms.Application.AddMessageFilter%2A> hinzu.</li><li>Entfernt einen Nachrichtenfilter durch Aufrufen der Methode <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. -Methode.</li></ul></li><li>**Und** ruft Nachrichten durch Aufrufen der <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>-Methode ab.</li></ul><br /> Derartige Implementierungen in Windows Forms-Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, lösen in einigen Fällen eine <xref:System.IndexOutOfRangeException>-Ausnahme aus, wenn die <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>-Methode aufgerufen wird.|Diese Änderung wirkt sich auf alle Apps aus, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind. Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, sind nicht betroffen.<br /><br /> Für Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, kann dieses Verhalten jedoch deaktiviert werden. Darüber hinaus ist es möglich, dass dieses Verhalten für Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, aber unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden, aktiviert wird. Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|Kante|  
  
## <a name="see-also"></a>Siehe auch  
 [Anwendungskompatibilität in 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
