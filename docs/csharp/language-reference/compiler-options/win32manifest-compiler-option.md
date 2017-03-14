---
title: "/win32manifest (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/win32manifest"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/win32manifest compiler option [C#]"
  - "win32manifest compiler option [C#]"
  - "-win32manifest compiler option [C#]"
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /win32manifest (C# Compiler Options)
Geben Sie mit der **\/win32manifest**\-Option an, dass eine benutzerdefinierte Win32\-Anwendungsmanifestdatei in die übertragbare ausführbare Datei \(Portable Executable, PE\) eines Projekts eingebettet werden soll.  
  
## Syntax  
  
```  
/win32manifest: filename  
```  
  
## Argumente  
 `filename`  
 Name und Speicherort der benutzerdefinierten Manifestdatei  
  
## Hinweise  
 Standardmäßig bettet der [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)]\-Compiler ein Anwendungsmanifest ein, das die angeforderte Ausführungsebene "asInvoker" angibt. Sie erstellt das Manifest im gleichen Ordner, in dem die ausführbare Datei erstellt wird, in der Regel der Ordner bin\\Debug oder bin\\Release, wenn Sie Visual Studio verwenden.  Wenn Sie einer Zollerklärung angeben möchten, beispielsweise, um einer angeforderten Ausführungsebene anzugeben, die von "highestAvailable" oder "vom requireAdministrator, verwenden Sie diese Option, den Namen der Datei an.  
  
> [!NOTE]
>  Diese Option und die [\/win32res \(Import a Win32 Resource File\)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)\-Option schließen sich gegenseitig aus.  Wenn Sie in derselben Befehlszeile beide Optionen angeben, tritt ein Buildfehler auf.  
  
 Eine Anwendung ohne ein Anwendungsmanifest, das die angeforderte Ausführungsebene angibt, unterliegt der Datei\-\/Registrierungsvirtualisierung der Benutzerkontensteuerung von Windows Vista.  Weitere Informationen über Virtualisierung, Sie finden. [Die Windows Vista\-Entwickler\-Story: Windows Vista\-Anwendungsentwicklungs\-Anforderungen für User\-Account\-Control \(UAC\)](http://go.microsoft.com/fwlink/?LinkId=95452)  
  
 Eine Anwendung unterliegt der Virtualisierung, wenn eine der folgenden Bedingungen erfüllt ist:  
  
-   Sie verwenden die **\/nowin32manifest**\-Option, und Sie stellen in einem späteren Buildschritt oder als Teil einer RES\-Datei \(Windows\-Ressourcendatei\) über die **\/win32res**\-Option kein Manifest bereit.  
  
-   Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] erstellt eine Standardmanifestdatei und speichert diese zusammen mit der ausführbaren Datei in den Debug\- und Releaseverzeichnissen.  Sie können ihr eigenes Manifest hinzufügen, indem Sie es in einem Texteditor erstellen und die Datei dann zum Projekt hinzufügen.  Alternativ können Sie auch mit der rechten Maustaste auf das **Projekt**\-Symbol im **Projektmappen\-Explorer** klicken, **Neues Element hinzufügen** auswählen und dann auf **Anwendungsmanifestdatei** klicken.  Nachdem Sie die neue oder bestehende Manifestdatei hinzugefügt haben, wird sie in der Dropdownliste **Manifest** angezeigt.  Weitere Informationen finden Sie unter [Seite "Anwendung", Projekt\-Designer \(C\#\)](/visual-studio/ide/reference/application-page-project-designer-csharp).  
  
 Sie können das Anwendungsmanifest in einem benutzerdefinierten Postbuildschritt oder mit der [\/nowin32manifest \(No Win32 Manifest\)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)\-Option als Teil einer Win32\-Ressourcendatei bereitstellen.  Verwenden Sie dieselbe Option, wenn Sie möchten, dass Ihre Anwendung auf Windows Vista der Datei\- oder Registrierungsvirtualisierung unterliegt.  Hierdurch wird verhindert, dass der Compiler ein Standardmanifest erstellt und in die übertragbare ausführbare PE\-Datei einbettet.  
  
## Beispiel  
 Das folgende Beispiel enthält das Standardmanifest, das vom Visual C\#\-Compiler in eine PE eingefügt wird.  
  
> [!NOTE]
>  Der Compiler fügt die Standardanwendung "MyApplication.app" in die XML\-Datei ein.  Dies ist eine Problemumgehung, damit Anwendungen auf Windows Server 2003, Service Pack 3 ausgeführt werden.  
  
```  
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
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [\/nowin32manifest \(No Win32 Manifest\)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)