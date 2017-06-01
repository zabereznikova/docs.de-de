---
title: "Registering Assemblies with COM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM interop, registering assemblies"
  - "unregistering assemblies"
  - "interoperation with unmanaged code, registering assemblies"
  - "registering assemblies"
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Registering Assemblies with COM
Um eine Assembly in COM zu registrieren oder eine Registrierung aufzuheben, können Sie ein Befehlszeilentool namens [Assembly Registration\-Tool \(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) ausführen.  Mit Regasm.exe werden Informationen über die Klasse der Systemregistrierung hinzugefügt, sodass COM\-Clients das .NET Framework\-Klasse transparent verwenden können.  Die <xref:System.Runtime.InteropServices.RegistrationServices>\-Klasse stellt die entsprechenden Funktionen zur Verfügung.  
  
 Eine verwaltete Komponente muss in der Windows\-Registrierung registriert werden, damit sie von COM\-Clients aktiviert werden kann.  In der folgenden Tabelle werden die Schlüssel dargestellt, die durch **Regasm.exe** gewöhnlich in der Windows\-Registrierung eingetragen werden.  \(000000 gibt den eigentlichen GUID\-Wert an.\)  
  
|GUID|Beschreibung|Registrierungsschlüssel|  
|----------|------------------|-----------------------------|  
|CLSID|Klassenbezeichner|HKEY\_CLASSES\_ROOT\\CLSID\\{000…000}|  
|IID|Schnittstellenbezeichner|HKEY\_CLASSES\_ROOT\\Interface\\{000…000}|  
|LIBID|Bibliotheksbezeichner|HKEY\_CLASSES\_ROOT\\TypeLib\\{000…000}|  
|ProgID|Programmbezeichner|HKEY\_CLASSES\_ROOT\\000…000|  
  
 Unter dem HKCR\\CLSID\\{0000…0000}\-Schlüssel ist der Standardwert auf die ProgID der Klasse festgelegt, und zwei neue benannte Werte, Class und Assembly, werden hinzugefügt.  Der Assemblywert wird von Common Language Runtime in der Registrierung gelesen und an den Assemblyresolver von Common Language Runtime weitergeleitet.  Mithilfe von Assemblyinformationen wie Name und Versionsnummer sucht der Assemblyresolver nach der Assembly.  Zum Suchen einer Assembly durch den Assemblyresolver muss sich die Assembly an einem der folgenden Speicherorte befinden:  
  
-   Globaler Assemblycache \(es muss sich um eine Assembly mit starkem Namen handeln\).  
  
-   Anwendungsverzeichnis.  Auf Assemblys, die aus dem Anwendungspfad geladen werden, kann nur aus der Anwendung zugegriffen werden.  
  
-   Dateipfad zu **Regasm.exe**, der mit der **\/codebase**\-Option festgelegt wurde.  
  
 Regasm.exe erstellt auch den InProcServer32\-Schlüssel unter dem HKCR\\CLSID\\{0000…0000}\-Schlüssel.  Als Standardwert für den Schlüssel wird der Name der DLL\-Datei festgelegt, die die Common Language Runtime initialisiert \(**Mscoree.dll** \).  
  
## Untersuchen von Registrierungseinträgen  
 In COM\-Interop steht eine standardmäßige Klassenfactoryimplementierung zum Erstellen einer Instanz einer beliebigen .NET Framework\-Klasse zur Verfügung.  Clients können **DllGetClassObject** für die verwaltete DLL\-Datei aufrufen, um wie für eine beliebige andere COM\-Komponente eine Klassenfactory zu erhalten und Objekte zu erstellen.  
  
 Für den `InprocServer32` Unterschlüssel wird ein Verweis auf Mscoree.dll anstelle einer traditionellen COM\-Typbibliothek, anzugeben, dass die Common Language Runtime das verwaltete Objekt erstellt.  
  
## Siehe auch  
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [How to: Reference .NET Types from COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/de-de/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/de-de/fb63564c-c1b9-4655-a094-a235625882ce)