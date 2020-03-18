---
title: 'Vorgehensweise: Deaktivieren des Features zur Umgehung von starken Namen'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, loading into trusted application domains
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
ms.openlocfilehash: a4c4ae7ea61a659d3bede532da3c1bdaea448873
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141098"
---
# <a name="how-to-disable-the-strong-name-bypass-feature"></a>Vorgehensweise: Deaktivieren des Features zur Umgehung von starken Namen
Ab .NET Framework Version 3.5 Service Pack 1 (SP1) werden Signaturen mit starkem Namen nicht überprüft, wenn ein Assembly in ein vollständig vertrauenswürdiges <xref:System.AppDomain>-Objekt geladen wird, wie etwa die Standard-<xref:System.AppDomain> für die `MyComputer`-Zone. Dies wird Strong-Name-Bypass-Funktion genannt. In einer vollständig vertrauenswürdigen Umgebung sind Forderungen nach <xref:System.Security.Permissions.StrongNameIdentityPermission> für signierte, vollständig vertrauenswürdige Assemblys immer erfolgreich, unabhängig von deren Signatur. Einzige Einschränkung ist die Tatsache, dass die Assembly vollständig vertrauenswürdig sein muss, da deren Zone vollständig vertrauenswürdig ist. Da der starke Name unter diesen Bedingungen kein bestimmender Faktor ist, gibt es auch keinen Grund, ihn zu validieren. Das Umgehen der Validierung einer Signatur mit starkem Namen führt zu deutlichen Verbesserungen in der Leistung.  
  
 Die Bypass-Funktion gilt für alle vollständig vertrauenswürdigen Assemblys, die nicht verzögert signiert wurden, und die in eine vollständig vertrauenswürdige <xref:System.AppDomain> aus einem von der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft angegebenen Verzeichnis geladen wurden.  
  
 Sie können die Bypass-Funktion für alle Anwendungen auf einem Computer deaktivieren, indem Sie einen Wert für den Registrierungsschlüssel festlegen. Sie können die Einstellung für eine einzelne Anwendung deaktivieren, indem Sie eine Anwendungskonfigurationsdatei verwenden. Sie können die Bypass-Funktion nicht für eine einzelne Anwendung wiederherstellen, wenn sie vom Registrierungsschlüssel deaktiviert wurde.  
  
 Wenn Sie die Bypass-Funktion deaktivieren, wird der starke Name nur auf Korrektheit geprüft. Er wird nicht auf <xref:System.Security.Permissions.StrongNameIdentityPermission> geprüft. Wenn Sie einen bestimmten starken Namen überprüfen möchten, müssen Sie diesen Test separat durchführen.  
  
> [!IMPORTANT]
> Ob Sie die Möglichkeit haben, die Validierung eines starken Namens zu erzwingen, hängt vom Registrierungsschlüssel ab, wie in folgender Prozedur beschrieben. Wenn eine Anwendung unter einem Konto ausgeführt wird, dass keine ACL-Berechtigung (Access Control List) hat, um auf diesen Registrierungsschlüssel zuzugreifen, ist diese Einstellung unwirksam. Sie müssen sicherstellen, dass die ACL-Rechte für diesen Schlüssel so konfiguriert sind, dass er für alle Assemblys gelesen werden kann.  
  
## <a name="disable-the-strong-name-bypass-feature-for-all-applications"></a>Deaktivieren des Features zur Umgehung von starken Namen für alle Anwendungen  
  
- Erstellen Sie auf 32-Bit-Computern einen DWORD-Eintrag mit einem Wert von 0 (null) mit dem Namen `AllowStrongNameBypass` unter dem Schlüssel „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework“ in der Registrierung des Systems.  
  
- Erstellen Sie auf 64-Bit-Computern einen DWORD-Eintrag mit einem Wert von 0 (null) mit dem Namen `AllowStrongNameBypass` unter den Schlüsseln „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework“ und „HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework“ in der Registrierung des Systems.  
  
## <a name="disable-the-strong-name-bypass-feature-for-a-single-application"></a>Deaktivieren des Features zur Umgehung von starken Namen für eine einzelne Anwendung  
  
1. Öffnen oder erstellen Sie die Anwendungskonfigurationsdatei.  
  
    Weitere Informationen zu dieser Datei finden Sie im Abschnitt zu Anwendungskonfigurationsdateien unter [Konfigurieren von Apps](../../framework/configure-apps/index.md).  
  
2. Fügen Sie folgenden Eintrag hinzu:  
  
    ```xml  
    <configuration>  
      <runtime>  
        <bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 Sie können das Umgehungsfeature für die Anwendung wiederherstellen, indem Sie die Einstellung der Konfigurationsdatei entfernen oder das Attribut auf `true` festlegen.  
  
> [!NOTE]
> Sie können die Überprüfung von starken Namen für eine Anwendung nur dann aktivieren oder deaktivieren, wenn die Bypass-Funktion auf dem Computer aktiviert ist. Wenn die Bypass-Funktion auf dem Computer deaktiviert wurde, werden starke Namen für alle Anwendungen überprüft, und Sie können die Überprüfung nicht für eine einzelne Anwendung umgehen.  
  
## <a name="see-also"></a>Siehe auch

- [Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md)
- [\<bypassTrustedAppStrongNames>-Element](../../framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)
- [Erstellen und Verwenden von Assemblys mit starkem Namen](create-use-strong-named.md)
