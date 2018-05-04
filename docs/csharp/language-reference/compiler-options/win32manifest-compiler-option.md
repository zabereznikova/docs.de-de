---
title: -win32manifest (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32manifest
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cb05f4f01dd7e19d2034de89ac47304b0731ca01
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="-win32manifest-c-compiler-options"></a>-win32manifest (C#-Compileroptionen)
Verwenden Sie die Option **-win32manifest**, um eine benutzerdefinierte Win32-Anwendungsmanifestdatei anzugeben, die in die übertragbare ausführbare Datei (portable executable, PE) eines Projekts eingebettet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-win32manifest: filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Der Name und Speicherort der benutzerdefinierten Manifestdatei  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig bettet der Visual C#-Compiler ein Anwendungsmanifest ein, das eine angeforderte Ausführungsebene als „asInvoker“ angibt. Er erstellt das Manifest in demselben Ordner, in dem die ausführbare Datei erstellt wird; in der Regel ist dies der Ordner „bin\Debug“ oder „bin\Release“, wenn Sie Visual Studio verwenden. Wenn Sie ein benutzerdefiniertes Manifest bereitstellen möchten, z.B. um eine angeforderte Ausführungsebene von „highestAvailable“ oder „requireAdministrator“ anzugeben, verwenden Sie diese Option zum Angeben des Dateinamens.  
  
> [!NOTE]
>  Diese Option und die Option [-win32res (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) schließen sich gegenseitig aus. Wenn Sie versuchen, beide Optionen in derselben Befehlszeile zu verwenden, erhalten Sie einen Buildfehler.  
  
 Eine Anwendung ohne Anwendungsmanifest, das eine angeforderte Ausführungsebene angibt, unterliegt der Datei- und Registrierungsvirtualisierung unter der Benutzerkontensteuerung in Windows. Weitere Informationen finden Sie unter [Benutzerkontensteuerung](/windows/access-protection/user-account-control/user-account-control-overview).  
  
 Die Anwendung unterliegt der Virtualisierung, wenn eine dieser Bedingungen erfüllt ist:  
  
-   Sie verwenden die Option **-nowin32manifest** und stellen in einem späteren Buildschritt oder als Teil einer Windows-Ressource (.res) kein Manifest bereit, indem Sie die Option **-win32res** verwenden.  
  
-   Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] erstellt eine Standard MANIFEST-Datei und speichert sie zusammen mit der ausführbaren Datei in den Debug- oder Releaseverzeichnissen. Sie können ein benutzerdefiniertes Manifest hinzufügen, indem Sie es in einem Text-Editor erstellen und die Datei anschließend zum Projekt hinzufügen. Alternativ können Sie mit der rechten Maustaste auf das **Projekt**-Symbol im **Projektmappen-Explorer** klicken und anschließend auf **Neues Element hinzufügen** und dann auf **Anwendungsmanifestdatei** klicken. Nachdem Sie Ihre neue oder vorhandene Manifestdatei hinzugefügt haben, wird sie in der Dropdownliste **Manifest** angezeigt. Weitere Informationen finden Sie unter [Seite „Anwendung“, Projekt-Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Sie können das Anwendungsmanifest über einen benutzerdefinierten Postbuildschritt oder als Teil einer Win32-Ressourcendatei bereitstellen, indem Sie die Option [-nowin32manifest (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) verwenden. Verwenden Sie dieselbe Option, wenn Ihre Anwendung der Datei- oder Registrierungsvirtualisierung unter Windows Vista unterliegen soll. Dies verhindert, dass der Compiler ein Standardmanifest in der portierbaren ausführbaren Datei (portable executable, PE) erstellt und einbettet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Standardmanifest gezeigt, das der Visual C# Compiler in eine PE einfügt.  
  
> [!NOTE]
>  Der Compiler fügt einen Standardanwendungsnamen, „MyApplication.app“, in die XML-Datei ein. Mit dieser Problemumgehung können Anwendungen unter Windows Server 2003 Service Pack 3 ausgeführt werden.  
  
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
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [-nowin32manifest (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
