---
title: Interoperabilität mit nicht verwaltetem Code
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: 12183f390a5178f038c6dd2122a72a33e31ae0ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457964"
---
# <a name="interoperating-with-unmanaged-code"></a>Interoperabilität mit nicht verwaltetem Code

.NET Framework stuft die Interaktion mit COM-Komponenten, COM+-Diensten, externen Typbibliotheken und vielen Betriebssystemdiensten herauf. Datentypen, Methodensignaturen und Mechanismen zur Behandlung von Fehlern variieren zwischen verwalteten und nicht verwalteten Objektmodellen. Um die Interoperation zwischen .NET Framework-Komponenten und nicht verwaltetem Code sowie den Migrationspfad zu vereinfachen, verbirgt die Common Language Runtime die Unterschiede in diesen Objektmodellen vor jeweils Clients und Servern.

Code, der unter der Kontrolle der Runtime ausgeführt wird, wird als verwalteter Code bezeichnet. Umgekehrt wird Code, der außerhalb der Runtime ausgeführt wird, wird als nicht verwalteter Code bezeichnet. Beispiele für nicht verwalteten Code sind COM-Komponenten, ActiveX-Schnittstellen und Windows API-Funktionen.

## <a name="in-this-section"></a>In diesem Abschnitt

[Verfügbarmachen von COM-Komponenten für .NET Framework](exposing-com-components.md)  
Beschreibt, wie COM-Komponenten aus .NET Framework-Anwendungen verwendet werden

[Verfügbarmachen von .NET Framework-Komponenten in COM](exposing-dotnet-components-to-com.md)  
Beschreibt, wie .NET Framework-Komponenten aus COM-Anwendungen verwendet werden

[Verwenden nicht verwalteter DLL-Funktionen](consuming-unmanaged-dll-functions.md)  
Beschreibt das Aufrufen von nicht verwalteten DLL-Funktionen mithilfe von Plattformaufruf

[Interop Marshaling (Interop-Marshalling)](interop-marshaling.md)  
Beschreibt das Marshalling für COM-Interop sowie Plattformaufruf

[How to: Zuordnen von HRESULT-Werten und Ausnahmen](how-to-map-hresults-and-exceptions.md)  
Beschreibt die Zuordnung zwischen Ausnahmen und HRESULTs

[Typäquivalenz und eingebettete Interop-Typen](type-equivalence-and-embedded-interop-types.md)  
Beschreibt, wie die Typinformation für COM-Typen in Assemblys eingebettet wird und wie die Common Language Runtime die Äquivalenz von eingebetteten COM-Typen bestimmt

[How to: Generieren primärer Interopassemblys mit „Tlbimp.exe“](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
Beschreibt, wie primäre Interop-Assemblys mit *Tlbimp.exe* (Type Library Importer-Tool) erstellt werden

[How to: Registrieren primärer Interopassemblys](how-to-register-primary-interop-assemblies.md)  
Beschreibt, wie die primären Interop-Assemblys registriert werden, bevor Sie in Ihren Projekten auf diese verweisen können

[COM-Interop ohne Registrierung](registration-free-com-interop.md)  
Beschreibt, wie COM-Interop Komponenten aktivieren kann, ohne die Windows-Registrierung zu verwenden

[How to: Konfigurieren von .NET Framework-basierten COM-Komponenten für die Aktivierung ohne Registrierung](configure-net-framework-based-com-components-for-reg.md)  
Beschreibt, wie ein Anwendungsmanifest erstellt wird und wie ein Komponentenmanifest erstellt und eingebettet wird

## <a name="related-sections"></a>Verwandte Abschnitte

[COM-Wrapper](../../standard/native-interop/com-wrappers.md)  
Beschreibt die von COM-Interop bereitgestellten Wrapper
