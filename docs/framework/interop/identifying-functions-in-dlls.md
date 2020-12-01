---
title: Identifizieren von Funktionen in DLLs
description: Identifizieren Sie Funktionen in DLLs. Die Identität einer DLL-Funktion besteht aus einem Funktionsnamen oder einer Ordinalzahl und dem DLL-Dateinamen, in dem die Implementierung zu finden ist.
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
ms.openlocfilehash: b1d95329e9b8ac6cd1f8ffc3111a50b6ab010462
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281715"
---
# <a name="identifying-functions-in-dlls"></a>Identifizieren von Funktionen in DLLs

Die Identität einer DLL-Funktion besteht aus den folgenden Elementen:  
  
- Funktionsname oder Ordinalzahl  
  
- Name der DLL-Datei, in der die Implementierung gefunden werden kann  
  
 Die Angabe der **MessageBox**-Funktion in der „User32.dll“ gibt beispielsweise die Funktion (**MessageBox**) und deren Speicherort (User32.dll, User32 oder user32) an. Die Microsoft Windows-Anwendungsprogrammierschnittstelle (Windows-API) kann zwei Versionen jeder Funktion enthalten, die Zeichen und Zeichenfolgen verarbeitet: eine ANSI-Version mit 1-Byte-Zeichen und eine Unicode-Version mit 2-Byte-Zeichen. Ohne Angabe wird der Zeichensatz, der durch das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>-Feld dargestellt wird, standardmäßig auf ANSI festgelegt. Einige Funktionen können über mehr als zwei Versionen verfügen.  
  
 **MessageBoxA** ist der ANSI-Einstiegspunkt für die **MessageBox**-Funktion. **MessageBoxW** ist die Unicode-Version. Sie können Funktionsnamen für eine bestimmte DLL-Datei, z.B. „User32.dll“, auflisten, indem Sie eine Vielzahl von Befehlszeilentools ausführen. Beispielsweise können Sie `dumpbin /exports user32.dll` oder `link /dump /exports user32.dll` verwenden, um Funktionsnamen abzurufen.  
  
 Sie können eine nicht verwaltete Funktion innerhalb des Codes beliebig umbenennen, solange Sie den neuen Namen für den ursprünglichen Einstiegspunkt in der DLL zuordnen. Anweisungen zur Umbenennung einer nicht verwalteten DLL-Funktion in verwaltetem Quellcode finden Sie unter [Angeben eines Einstiegspunktes](specifying-an-entry-point.md).  
  
 Durch einen Plattformaufruf können Sie einen beträchtlichen Teil des Betriebssystems durch Aufrufen von Funktionen in der Windows-API und anderen DLLs steuern. Zusätzlich zur Windows-API stehen Ihnen über den Plattformaufruf zahlreiche andere APIs und DLLs zur Verfügung.  
  
 Die folgende Tabelle beschreibt einige häufig verwendete DLLs in der Windows-API.  
  
|DLL|Inhaltsbeschreibung|  
|---------|-----------------------------|  
|GDI32.dll|Funktionen für Graphics Device Interface (GDI) für Geräteausgaben, wie z.B. die für die Verwaltung der Zeichnung und Schriftart.|  
|Kernel32.dll|Betriebssystemfunktionen auf niedriger Ebene für die Verwaltung des Arbeitsspeichers und Ressourcenbehandlung.|  
|User32.dll|Windows-Verwaltungsfunktionen für Meldungsbehandlung, Timer, Menüs und Kommunikation.|  
  
 Eine vollständige Dokumentation der Windows-API finden Sie im Plattform SDK. Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden nicht verwalteter DLL-Funktionen](consuming-unmanaged-dll-functions.md)
- [Angeben eines Einstiegspunktes](specifying-an-entry-point.md)
- [Erstellen einer Klasse zum Halten von DLL-Funktionen](creating-a-class-to-hold-dll-functions.md)
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](creating-prototypes-in-managed-code.md)
- [Calling a DLL Function (Aufrufen einer DLL-Funktion)](calling-a-dll-function.md)
