---
title: "Packaging an Assembly for COM | Microsoft Docs"
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
  - "exposing .NET Framework components to COM"
  - "COM interop, packaging assemblies"
  - "packaging assemblies for COM"
  - "Tlbexp.exe"
  - "TypeLibConverter class"
  - ".NET Services Installation tool"
  - "Assembly Registration tool"
  - "Type Library Exporter"
  - "Reqsvcs.exe"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "interoperation with unmanaged code, packaging assemblies"
  - "COM interop, exposing COM components"
  - "Reqasm.exe"
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Packaging an Assembly for COM
Folgende Informationen über verwaltete Typen, die in Anwendungen eingebunden werden sollen, sind für COM\-Entwickler von Nutzen:  
  
-   Eine Liste mit allen Typen, die von COM\-Anwendungen verarbeitet werden können.  
  
     Einige der verwalteten Typen werden in COM nicht angezeigt; andere können angezeigt, aber nicht erstellt werden; wieder andere können sowohl angezeigt als auch erstellt werden.  In einer Assembly können alle Kombinationen von unsichtbaren, sichtbaren, erstellbaren und nicht erstellbaren Typen enthalten sein.  Der Vollständigkeit halber identifizieren Sie die Typen in einer Assembly, die Sie in COM verfügbar machen möchten. Dies ist insbesondere dann wichtig, wenn es sich bei diesen Typen um eine Teilmenge der Typen handelt, die in .NET Framework zugänglich sind.  
  
     Weitere Informationen finden Sie unter [Qualifizieren von .NET\-Typen für die Interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).  
  
-   Anweisungen zum Versioning  
  
     Verwaltete Klassen, welche die Klassenschnittstelle \(eine von COM\-Interop generierte Schnittstelle\) implementieren, unterliegen Beschränkungen beim Versioning.  
  
     Die Richtlinien zum Verwenden der Klassenschnittstelle finden Sie unter [Einführung in die Klassenschnittstelle](http://msdn.microsoft.com/de-de/733c0dd2-12e5-46e6-8de1-39d5b25df024).  
  
-   Anweisungen zur Bereitstellung  
  
     Assemblys mit starken Namen und der Signatur des Herausgebers können im globalen Assemblycache installiert werden.  Unsignierte Assemblys müssen auf dem Computer des Benutzers als private Assemblys installiert werden.  
  
     Weitere Informationen finden Sie unter [Überlegungen zur Assemblysicherheit](../../../docs/framework/app-domains/assembly-security-considerations.md).  
  
-   Einbindung der Typbibliothek  
  
     Für die meisten Typen ist eine Typbibliothek erforderlich, damit sie von einer COM\-Anwendung verarbeitet werden können.  Eine Typbibliothek können Sie selbst generieren oder von einem COM\-Entwickler erstellen lassen.  [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] bietet die folgenden Optionen zum Generieren einer Typbibliothek:  
  
    -   [Type Library Exporter\-Tool](#cpconpackagingassemblyforcomanchor1)  
  
    -   [TypeLibConverter\-Klasse](#cpconpackagingassemblyforcomanchor2)  
  
    -   [Assembly Registration\-Tool](#cpconpackagingassemblyforcomanchor3)  
  
    -   [.NET Services Installation\-Tool](#cpconpackagingassemblyforcomanchor4)  
  
     Unabhängig davon, welchen Mechanismus Sie wählen, werden nur die öffentlichen Typen in die generierte Typbibliothek aufgenommen, die in der von Ihnen bereitgestellten Assembly definiert sind.  
  
     Sie können eine Typbibliothek als separate Datei packen oder als Win32\-Ressourcendatei in eine .NET\-basierte Anwendung einbetten.  Microsoft Visual Basic 6.0 führt diese Aufgabe automatisch aus. Wenn Sie jedoch [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] verwenden, müssen Sie die Typbibliothek manuell einbetten.  Anweisungen finden Sie unter [Gewusst wie: Einbetten von Typbibliotheken als Win32\-Ressourcen in .NET\-Anwendungen](http://msdn.microsoft.com/de-de/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44).  
  
<a name="cpconpackagingassemblyforcomanchor1"></a>   
## Type Library Exporter\-Tool  
 Mit dem Befehlszeilentool [Type Library Exporter \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) können Sie Klassen und Schnittstellen, die in einer Assembly enthalten sind, in eine COM\-Typbibliothek konvertieren.  Sobald die Typinformationen der Klasse verfügbar sind, können die COM\-Clients eine Instanz der .NET\-Klasse erstellen und die Methoden der Instanz aufrufen, als wäre es ein COM\-Objekt.  Mit **Tlbexp.exe** wird eine vollständige Assembly auf einmal konvertiert.  Sie können mit **Tlbexp.exe** keine Typinformationen für einen Teil der in der Assembly definierten Typen generieren.  
  
<a name="cpconpackagingassemblyforcomanchor2"></a>   
## TypeLibConverter\-Klasse  
 Mit der im **System.Runtime.Interop**\-Namespace enthaltenen <xref:System.Runtime.InteropServices.TypeLibConverter>\-Klasse werden die in einer Assembly enthaltenen Klassen und Schnittstellen in eine COM\-Typbibliothek konvertiert.  Mit dieser API werden dieselben Typinformationen erstellt wie mit dem im vorherigen Abschnitt beschriebenen Type Library Exporter\-Tool.  
  
 Die **TypeLibConverter\-Klasse** implementiert die [ItypeLibConverter\-Schnittstelle](frlrfSystemRuntimeInteropServicesITypeLibConverterClassTopic).  
  
<a name="cpconpackagingassemblyforcomanchor3"></a>   
## Assembly Registration\-Tool  
 Mit dem [Assembly Registration\-Tool \(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) können Sie eine Typbibliothek generieren und registrieren, wenn Sie die **\/tlb:**\-Option anwenden.  Für COM\-Clients müssen die Typbibliotheken in der Windows\-Registrierung installiert werden.  Ohne diese Option registriert **Regasm.exe** die Typen nur in einer Assembly, nicht in der Typbibliothek.  Das Registrieren von Typen in einer Assembly und das Registrieren der Typbibliothek sind verschiedene Aktivitäten.  
  
<a name="cpconpackagingassemblyforcomanchor4"></a>   
## .NET Services Installation\-Tool  
 Mit dem [.NET Services Installation\-Tool \(Regsvcs.exe\)](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md) werden verwaltete Klassen zum Windows 2000\-Komponentendienst hinzugefügt und mehrere Aufgaben in einem einzelnen Tool kombiniert.  Zusätzlich zum Laden und Registrieren der Assembly kann mithilfe von **Regsvcs.exe** auch die Typbibliothek generiert, registriert und in einer vorhandenen COM\+ 1.0\-Anwendung installiert werden.  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 <xref:System.Runtime.InteropServices.ITypeLibConverter>   
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Qualifying .NET Types for Interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/de-de/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Überlegungen zur Assemblysicherheit](../../../docs/framework/app-domains/assembly-security-considerations.md)   
 [Tlbexp.exe \(Type Library Exporter\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)   
 [Registering Assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [How to: Embed Type Libraries as Win32 Resources in Applications](http://msdn.microsoft.com/de-de/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44)