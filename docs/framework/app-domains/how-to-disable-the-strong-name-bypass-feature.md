---
title: 'Gewusst wie: Deaktivieren des Strong-Name-Bypass-Features'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, loading into trusted application domains
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
caps.latest.revision: "30"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fe694f9324a67e1ffa3eacf16cfbfcc266550693
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-the-strong-name-bypass-feature"></a>Gewusst wie: Deaktivieren des Strong-Name-Bypass-Features
Ab .NET Framework Version 3.5 Service Pack 1 (SP1) werden Signaturen mit starkem Namen nicht überprüft, wenn ein Assembly in ein vollständig vertrauenswürdiges <xref:System.AppDomain>-Objekt geladen wird, wie etwa die Standard-<xref:System.AppDomain> für die `MyComputer`-Zone. Dies wird Strong-Name-Bypass-Funktion genannt. In einer vollständig vertrauenswürdigen Umgebung sind Forderungen nach <xref:System.Security.Permissions.StrongNameIdentityPermission> für signierte, vollständig vertrauenswürdige Assemblys immer erfolgreich, unabhängig von deren Signatur. Einzige Einschränkung ist die Tatsache, dass die Assembly vollständig vertrauenswürdig sein muss, da deren Zone vollständig vertrauenswürdig ist. Da der starke Name unter diesen Bedingungen kein bestimmender Faktor ist, gibt es auch keinen Grund, ihn zu validieren. Das Umgehen der Validierung einer Signatur mit starkem Namen führt zu deutlichen Verbesserungen in der Leistung.  
  
 Die Bypass-Funktion gilt für alle vollständig vertrauenswürdigen Assemblys, die nicht verzögert signiert wurden, und die in eine vollständig vertrauenswürdige <xref:System.AppDomain> aus einem von der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft angegebenen Verzeichnis geladen wurden.  
  
 Sie können die Bypass-Funktion für alle Anwendungen auf einem Computer deaktivieren, indem Sie einen Wert für den Registrierungsschlüssel festlegen. Sie können die Einstellung für eine einzelne Anwendung deaktivieren, indem Sie eine Anwendungskonfigurationsdatei verwenden. Sie können die Bypass-Funktion nicht für eine einzelne Anwendung wiederherstellen, wenn sie vom Registrierungsschlüssel deaktiviert wurde.  
  
 Wenn Sie die Bypass-Funktion deaktivieren, wird der starke Name nur auf Korrektheit geprüft. Er wird nicht auf <xref:System.Security.Permissions.StrongNameIdentityPermission> geprüft. Wenn Sie einen bestimmten starken Namen überprüfen möchten, müssen Sie diesen Test separat durchführen.  
  
> [!IMPORTANT]
>  Ob Sie die Möglichkeit haben, die Validierung eines starken Namens zu erzwingen, hängt vom Registrierungsschlüssel ab, wie in folgender Prozedur beschrieben. Wenn eine Anwendung unter einem Konto ausgeführt wird, dass keine ACL-Berechtigung (Access Control List) hat, um auf diesen Registrierungsschlüssel zuzugreifen, ist diese Einstellung unwirksam. Sie müssen sicherstellen, dass die ACL-Rechte für diesen Schlüssel so konfiguriert sind, dass er für alle Assemblys gelesen werden kann.  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-all-applications"></a>So können Sie die Strong-Name-Bypass-Funktion für alle Anwendungen deaktivieren  
  
-   Erstellen Sie auf 32-Bit-Computern einen DWORD-Eintrag mit einem Wert von 0 (null) mit dem Namen `AllowStrongNameBypass` unter dem Schlüssel „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework“ in der Registrierung des Systems.  
  
-   Erstellen Sie auf 64-Bit-Computern einen DWORD-Eintrag mit einem Wert von 0 (null) mit dem Namen `AllowStrongNameBypass` unter den Schlüsseln „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework“ und „HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework“ in der Registrierung des Systems.  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-a-single-application"></a>So können Sie die Strong-Name-Bypass-Funktion für eine Anwendung deaktivieren  
  
1.  Öffnen oder erstellen Sie die Anwendungskonfigurationsdatei.  
  
     Weitere Informationen zu dieser Datei finden Sie im Abschnitt zu Anwendungskonfigurationsdateien unter [Configuring Apps (Konfigurationsdateien)](../../../docs/framework/configure-apps/index.md).  
  
2.  Fügen Sie folgenden Eintrag hinzu:  
  
    ```xml  
    <configuration>  
      <runtime>  
        <bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 Sie können die Bypass-Funktion für die Anwendung wieder aktivieren, indem Sie die Einstellung der Konfigurationsdatei entfernen oder das Attribut auf „TRUE“ festlegen.  
  
> [!NOTE]
>  Sie können die Überprüfung von starken Namen für eine Anwendung nur dann aktivieren oder deaktivieren, wenn die Bypass-Funktion auf dem Computer aktiviert ist. Wenn die Bypass-Funktion auf dem Computer deaktiviert wurde, werden starke Namen für alle Anwendungen überprüft, und Sie können die Überprüfung nicht für eine einzelne Anwendung umgehen.  
  
## <a name="see-also"></a>Siehe auch  
 [Sn.exe (Strong Name-Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 [\<BypassTrustedAppStrongNames >-Element](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)  
 [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
