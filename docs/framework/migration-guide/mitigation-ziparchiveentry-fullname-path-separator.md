---
title: 'Entschärfung: Pfadtrennzeichen für ZipArchiveEntry.FullName'
ms.date: 03/30/2017
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
ms.openlocfilehash: 3f6c7f258fd5dbf01db4d79b73b88ddd7484f9b2
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102618"
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>Entschärfung: Pfadtrennzeichen für ZipArchiveEntry.FullName

In allen Apps, die für .NET Framework 4.6.1 entwickelt wurden, ändert sich das in der Eigenschaft <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> verwendete Pfadtrennzeichen von einem umgekehrten Schrägstrich (\\) (Vorgängerversionen des .NET Framework) in einen einfachen Schrägstrich (/). <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType>-Objekte werden durch Aufrufen einer der Überladungen der <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>-Methode erstellt.  
  
## <a name="impact"></a>Auswirkungen  
 Die Änderung bringt die .NET-Implementierung in Einklang mit Abschnitt 4.4.17.1 der [ZIP-Dateiformatspezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) und ermöglicht es, dass ZIP-Archive auf Nicht-Windows-Systemen entpackt werden.  
  
 Beim Dekomprimieren einer ZIP-Datei, die für eine frühere Version des .NET Framework unter einem anderen als dem Windows-Betriebssystem – wie etwa macOS – erstellt wurde, bleibt die Verzeichnisstruktur nicht erhalten. Beispielsweise werden unter macOS mehrere Dateien erstellt, für deren Dateinamen der Verzeichnispfad mit umgekehrten Schrägstrichzeichen (\\) und dem Dateinamen verkettet wird. Im Ergebnis wird die Verzeichnisstruktur der dekomprimierten Dateien nicht beibehalten.  
  
 Die Auswirkungen dieser Änderungen auf ZIP-Dateien, die unter Windows durch die APIs im <xref:System.IO>-Namespace des .NET Framework dekomprimiert werden, sollten minimal sein, da diese APIs sowohl den einfachen Schrägstrich (/) als auch den umgekehrten Schrägstrich (\\) als Pfadtrennzeichen problemlos verarbeiten können.  
  
## <a name="mitigation"></a>Minderung  
 Wenn dieses Verhalten nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen. Im Folgenden sind sowohl der Abschnitt `<runtime>` als auch der Schalter zur Ablehnung dargestellt.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 Dieses Verhalten kann auch für Apps aktiviert werden, die für eine frühere Version des .NET Framework entwickelt wurden, aber in .NET Framework 4.6.1 und höher ausgeführt werden. Dazu müssen Sie dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei nur eine Konfigurationseinstellung hinzufügen. Im Folgenden sind sowohl der Abschnitt `<runtime>` als auch der Schalter zur Annahme dargestellt.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
