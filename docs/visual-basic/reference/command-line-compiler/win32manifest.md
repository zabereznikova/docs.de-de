---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cef1e6c19e7fdd6fc9f42c8fc36008314ea80a80
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349128"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`fileName`|Der Pfad der benutzerdefinierten Manifest-Datei.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig bettet der Visual Basic-Compiler ein Anwendungs Manifest ein, das die angeforderte Ausführungs Ebene "asInvoker" angibt. Er erstellt das Manifest im selben Ordner, in dem die ausführbare Datei erstellt wird. in der Regel ist dies der Ordner "bin\debug" oder "Bin\Release", wenn Sie Visual Studio verwenden. Wenn Sie ein benutzerdefiniertes Manifest angeben möchten, z. b. um die angeforderte Ausführungs Ebene "highestAvailable" oder "requiinfoministrator" anzugeben, verwenden Sie diese Option, um den Namen der Datei anzugeben.  
  
> [!NOTE]
> Diese Option und die Option " [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) " schließen sich gegenseitig aus. Wenn Sie versuchen, beide Optionen in derselben Befehlszeile zu verwenden, erhalten Sie einen Buildfehler.  
  
 Eine Anwendung ohne Anwendungsmanifest, das eine angeforderte Anwendungsebene angibt, unterliegt der Datei- und Registrierungsvirtualisierung unter der Benutzerkontensteuerung in Windows Vista. Weitere Informationen über Virtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Die Anwendung unterliegt der Virtualisierung, wenn eine der folgenden Bedingungen zutrifft:  
  
1. Mithilfe der Option `-nowin32manifest` können Sie in einem späteren Buildschritt oder als Teil einer Windows-Ressourcen Datei (. res) kein Manifest bereitstellen, indem Sie die `-win32resource`-Option verwenden.  
  
2. Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.  
  
 Visual Studio erstellt eine MANIFEST-Standarddatei und speichert sie zusammen mit der ausführbaren Datei in den Debug- oder Releaseverzeichnissen. Sie können die Standarddatei "App. Manifest" anzeigen oder bearbeiten, indem Sie im Projekt-Designer auf der Registerkarte **Anwendung** auf **UAC-Einstellungen anzeigen** klicken. Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Sie können das Anwendungs Manifest mithilfe der Option `-nowin32manifest` als benutzerdefinierten Postbuildschritt oder als Teil einer Win32-Ressourcen Datei bereitstellen. Verwenden Sie dieselbe Option, wenn Ihre Anwendung der Datei- oder Registrierungsvirtualisierung unter Windows Vista unterliegen soll. Dadurch wird verhindert, dass der Compiler ein Standard Manifest in die PE-Datei erstellt und einbettet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Standard Manifest, das der Visual Basic Compiler in ein PE einfügt.  
  
> [!NOTE]
> Der Compiler fügt den Standard Anwendungsnamen MyApplication. app in das Manifest-XML ein. Mit dieser Problemumgehung können Anwendungen unter Windows Server 2003 Service Pack 3 ausgeführt werden.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
