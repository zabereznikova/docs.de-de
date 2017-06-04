---
title: "Identifying Functions in DLLs | Microsoft Docs"
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
  - "platform invoke, identifying functions"
  - "COM interop, DLL functions"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "interoperation with unmanaged code, DLL functions"
  - "interoperation with unmanaged code, platform invoke"
  - "identifying DLL functions"
  - "DLL functions"
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Identifying Functions in DLLs
Die Identität einer DLL\-Funktion besteht aus folgenden Elementen:  
  
-   Funktionsname oder Ordinalzahl  
  
-   Name der DLL\-Datei, in der sich die Implementierung befindet  
  
 Wenn Sie z. B. die **MessageBox**\-Funktion in der Datei User32.dll angeben, werden Funktion \(**MessageBox**\) und Position \(User32.dll, User32 oder user32\) identifiziert.  Die Win32\-API \(Microsoft Windows Application Programming Interface\) kann zwei Versionen jeder Funktion enthalten, die Zeichen und Zeichenfolgen behandelt: eine Einzelbytezeichen\-Version \(ANSI\) und eine Doppelbytezeichen\-Version \(Unicode\).  Wenn kein Zeichensatz im <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>\-Feld angegeben ist, wird standardmäßig ANSI verwendet.  Einige Funktionen können mehr als zwei Versionen haben.  
  
 **MessageBoxA** ist der ANSI\-Einstiegspunkt für die **MessageBox**\-Funktion; **MessageBoxW** ist die Unicode\-Version.  Sie können Funktionsnamen für eine bestimmte DLL \(z. B. user32.dll\) auflisten, indem Sie verschiedene Befehlszeilentools ausführen.  Sie können z. B. `dumpbin /exports user32.dll` oder `link /dump /exports user32.dll` verwenden, um Funktionsnamen abzurufen.  
  
 Eine nicht verwaltete Funktion können Sie im Code beliebig umbenennen, solange Sie den neuen Namen zum ursprünglichen Einstiegspunkt in der DLL zuordnen.  Anweisungen zum Umbenennen einer nicht verwalteten DLL\-Funktion in verwaltetem Quellcode finden Sie unter [Angeben eines Einstiegspunkts](../../../docs/framework/interop/specifying-an-entry-point.md).  
  
 Mithilfe von Plattformaufrufen können Sie einen erheblichen Teil des Betriebssystems steuern, indem Sie Funktionen in der Win32\-API und anderen DLLs aufrufen.  Zusätzlich zur Win32\-API stehen Ihnen durch Plattformaufrufe zahlreiche weitere APIs und DLLs zur Verfügung.  
  
 In der folgenden Tabelle werden mehrere DLLs beschrieben, die häufig in der Win32\-API verwendet werden.  
  
|DLL|Inhaltsbeschreibung|  
|---------|-------------------------|  
|GDI32.dll|GDI \(Graphics Device Interface\)\-Funktionen für Geräteausgabe, z. B. Zeichnen und Zeichensatzverwaltung.|  
|Kernel32.dll|Betriebssystemfunktionen auf niedriger Ebene für Speicherverwaltung und Ressourcenbehandlung.|  
|User32.dll|Windows\-Verwaltungsfunktionen für Meldungsbehandlung, Timer, Menüs und Kommunikation.|  
  
 Eine vollständige Dokumentation der Win32\-API finden Sie unter Platform SDK.  Beispiele für das Erstellen von .NET\-basierten Deklarationen, die mit Plattformaufruf verwendet werden, finden Sie unter [Marshallen von Daten mit Plattformaufruf](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## Siehe auch  
 [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)   
 [Specifying an Entry Point](../../../docs/framework/interop/specifying-an-entry-point.md)   
 [Creating a Class to Hold DLL Functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Calling a DLL Function](../../../docs/framework/interop/calling-a-dll-function.md)