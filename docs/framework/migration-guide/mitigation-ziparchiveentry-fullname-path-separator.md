---
title: "Entschärfung: Pfadtrennzeichen für ZipArchiveEntry.FullName | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 747c98e0fd9db95c52531b398aa33161decac294
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>Entschärfung: Pfadtrennzeichen für ZipArchiveEntry.FullName
Von Apps für die Zielplattform [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] an wurde das in der Eigenschaft <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=fullName> verwendete Pfadtrennzeichen vom umgekehrten Schrägstrich („\\“), der in früheren Versionen von .NET Framework verwendet wurde, in einen einfachen Schrägstrich („/“) geändert.   <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=fullName>-Objekte werden durch Aufrufen einer der Überladungen der <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>-Methode erstellt.  
  
## <a name="impact"></a>Auswirkungen  
 Die Änderung bringt die .NET-Implementierung in Einklang mit Abschnitt 4.4.17.1 der [ZIP-Dateiformatspezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) und ermöglicht es, dass ZIP-Archive auf Nicht-Windows-Systemen entpackt werden.  
  
 Beim Dekomprimieren einer ZIP-Datei, die für eine frühere Version der .NET Framework-Zielplattform unter einem anderen als dem Windows-Betriebssystem – wie etwa dem Macintosh – erstellt wurde, bleibt die Verzeichnisstruktur nicht erhalten. Beispielsweise wird auf dem Macintosh ein Satz Dateien erstellt, deren Dateinamen eine Verkettung aus dem Verzeichnispfad mit allen ggf. vorhandenen umgekehrten Schrägstrichzeichen („\\“) darstellen. Im Ergebnis wird die Verzeichnisstruktur der dekomprimierten Dateien nicht beibehalten.  
  
 Die Auswirkungen dieser Änderungen auf ZIP-Dateien, die unter dem Windows-Betriebssystem durch die APIs im .NET Framework <xref:System.IO>-Namespace dekomprimiert werden, sollten minimal sein, da diese APIs sowohl den einfachen Schrägstrich („/“) als auch den umgekehrten Schrägstrich („\\“) als Pfadtrennzeichen verarbeiten können.  
  
## <a name="mitigation"></a>Problemumgehung  
 Wenn dieses Verhalten nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen. Im Folgenden sind sowohl der Abschnitt `<runtime>` als auch der Schalter zur Ablehnung dargestellt.  
  
```  
  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
  
```  
  
 Darüber hinaus können Apps mit früheren Versionen von .NET Framework als Zielplattform, die unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und höheren Versionen ausgeführt werden, sich für die Verwendung dieses Verhaltens entscheiden, indem sie dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen. Im Folgenden sind sowohl der Abschnitt `<runtime>` als auch der Schalter zur Annahme dargestellt.  
  
```  
  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)   
 [Anwendungskompatibilität in 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
