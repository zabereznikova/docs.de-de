---
title: "Gewusst wie: Deaktivieren des Strong-Name-Bypass-Features | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Strong-Name Bypass-Funktion"
  - "Assemblys mit starkem Namen, Laden in vertrauenswürdige Anwendungsdomänen"
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
caps.latest.revision: 30
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 30
---
# Gewusst wie: Deaktivieren des Strong-Name-Bypass-Features
Ab .NET Framework Version 3.5 Service Pack 1 \(SP1\) werden Signaturen mit starkem Namen nicht überprüft, wenn eine Assembly in ein vollständig vertrauenswürdiges <xref:System.AppDomain>\-Objekt, wie etwa die standardmäßige <xref:System.AppDomain> für die `MyComputer`\-Zone, geladen wird.  Dies wird als Strong\-Name\-Bypass\-Feature bezeichnet.  In einer vollständig vertrauenswürdigen Umgebung sind Forderungen nach <xref:System.Security.Permissions.StrongNameIdentityPermission> für signierte, vollständig vertrauenswürdige Assemblys unabhängig von deren Signatur stets erfolgreich.  Die einzige Beschränkung ist, dass die Assembly voll vertrauenswürdig sein muss, da deren Zone voll vertrauenswürdig ist.  Da der starke Name unter diesen Bedingungen kein entscheidender Faktor ist, besteht keine Veranlassung für dessen Validierung.  Die Umgehung der Validierung von Signaturen mit starkem Namen hat bedeutende Leistungsverbesserungen zur Folge.  
  
 Das Bypass\-Feature gilt für jede vollständig vertrauenswürdige Assembly, die nicht verzögert signiert wird und die in eine vollständig vertrauenswürdige <xref:System.AppDomain> aus dem durch ihre <xref:System.AppDomainSetup.ApplicationBase%2A>\-Eigenschaft festgelegten Verzeichnis geladen wird.  
  
 Sie können das Bypass\-Feature für alle Anwendungen auf einem Computer durch Festlegen eines Registrierungsschlüssels überschreiben.  Sie können die Einstellung für eine einzelne Anwendung mit einer Anwendungskonfigurationsdatei überschreiben.  Sie können das Bypass\-Feature nicht für eine einzelne Anwendung wiederherstellen, wenn dieses durch den Registrierungsschlüssels deaktiviert wurde.  
  
 Wenn Sie das Bypass\-Feature überschreiben, wird der starke Name nur auf Korrektheit hin überprüft, nicht jedoch auf eine <xref:System.Security.Permissions.StrongNameIdentityPermission>.  Wenn Sie einen bestimmten starken Namen bestätigen möchten, müssen Sie diese Überprüfung separat vornehmen.  
  
> [!IMPORTANT]
>  Die Möglichkeit, die Validierung eines starken Namens zu erzwingen, ist hängt von einem Registrierungsschlüssel ab. Dies wird in der folgenden Prozedur beschrieben.  Wenn eine Anwendung unter einem Konto ausgeführt wird, das nicht über die Zugriffssteuerungslisten \(ACL\)\-Berechtigung zum Zugriff auf diesen Registrierungsschlüssel verfügt, ist die Einstellung wirkungslos.  Stellen Sie sicher, dass ACL\-Berechtigungen für diesen Schlüssel konfiguriert werden, damit er für alle Assemblys lesbar ist.  
  
### So deaktivieren Sie das Strong\-Name\-Bypass\-Feature für alle Anwendungen  
  
-   Erstellen Sie auf 32\-Bit\-Computern in der Systemregistrierung unter dem Schlüssel HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework einen DWORD\-Eintrag mit dem Wert 0 und dem Namen `AllowStrongNameBypass`.  
  
-   Erstellen Sie auf 64\-Bit\-Computern in der Systemregistrierung unter den Schlüsseln HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework und HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework einen DWORD\-Eintrag mit dem Wert 0 und dem Namen `AllowStrongNameBypass`.  
  
### So deaktivieren Sie das Strong\-Name\-Bypass\-Feature für eine einzelne Anwendung  
  
1.  Öffnen oder erstellen Sie die Anwendungskonfigurationsdatei.  
  
     Weitere Informationen zu dieser Datei finden Sie im Abschnitt zu Anwendungskonfigurationsdateien in [Konfigurieren von Apps](../../../docs/framework/configure-apps/index.md).  
  
2.  Fügen Sie den folgenden Eintrag hinzu:  
  
    ```  
    <configuration>  
      <runtime>  
         < bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 Sie können das Bypass\-Feature für die Anwendung wiederherstellen, indem Sie die Konfigurationsdateieinstellung entfernen oder das Attribut auf "true" festlegen.  
  
> [!NOTE]
>  Sie können die Validierung von starken Namen für eine Anwendung nur ein\- und ausschalten, wenn das Bypass\-Feature für diesen Computer aktiviert ist.  Wenn das Bypass\-Feature für den Computer ausgeschaltet ist, werden starke Namen für alle Anwendungen validiert, und Sie können die Validierung nicht für eine einzelne Anwendung umgehen.  
  
## Siehe auch  
 [Sn.exe \(Strong Name Tool\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [\<bypassTrustedAppStrongNames\>\-Element](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)   
 [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)