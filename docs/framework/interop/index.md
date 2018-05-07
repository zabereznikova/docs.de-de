---
title: Interoperation mit nicht verwaltetem code
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 583cfb6e3a5145c6c0dfc82ec9ff64c6d87414ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="interoperating-with-unmanaged-code"></a>Interoperation mit nicht verwaltetem code

.NET Framework stuft die Interaktion mit COM-Komponenten, COM+-Diensten, externen Typbibliotheken und vielen Betriebssystemdiensten herauf. Datentypen, Methodensignaturen und Mechanismen zur Behandlung von Fehlern variieren zwischen verwalteten und nicht verwalteten Objektmodellen. Um die Interoperation zwischen .NET Framework-Komponenten und nicht verwaltetem Code sowie den Migrationspfad zu vereinfachen, verbirgt die Common Language Runtime die Unterschiede in diesen Objektmodellen vor jeweils Clients und Servern.

Code, der unter der Kontrolle der Runtime ausgeführt wird, wird als verwalteter Code bezeichnet. Umgekehrt wird Code, der außerhalb der Runtime ausgeführt wird, wird als nicht verwalteter Code bezeichnet. Beispiele für nicht verwalteten Code sind COM-Komponenten, ActiveX-Schnittstellen und Win32 API-Funktionen.

## <a name="in-this-section"></a>In diesem Abschnitt

[Verfügbarmachen von COM-Komponenten für .NET Framework](exposing-com-components.md)  
Beschreibt, wie COM-Komponenten aus .NET Framework-Anwendungen verwendet werden

[Verfügbarmachen von .NET Framework-Komponenten in COM](exposing-dotnet-components-to-com.md)  
Beschreibt, wie .NET Framework-Komponenten aus COM-Anwendungen verwendet werden

[Verwenden nicht verwalteter DLL-Funktionen](consuming-unmanaged-dll-functions.md)  
Beschreibt das Aufrufen von nicht verwalteten DLL-Funktionen mithilfe von Plattformaufruf

[Interop Marshaling (Interop-Marshalling)](interop-marshaling.md)  
Beschreibt das Marshalling für COM-Interop sowie Plattformaufruf

[Gewusst wie: Zuordnen von HRESULTs und Ausnahmen](how-to-map-hresults-and-exceptions.md)  
Beschreibt die Zuordnung zwischen Ausnahmen und HRESULTs

[COM-Wrapper](com-wrappers.md)  
Beschreibt die gebotenen COM-Interop-Wrapper.

[Typäquivalenz und eingebettete Interop-Typen](type-equivalence-and-embedded-interop-types.md)  
Beschreibt, wie die Typinformationen für COM-Typen in Assemblys eingebettet ist, und wie die common Language Runtime die Äquivalenz von eingebetteten COM-Typen bestimmt.

[Gewusst wie: Generieren primärer Interop-Assemblys mit "Tlbimp.exe"](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
Beschreibt, wie primäre Interop-Assemblys mit erzeugen *Tlbimp.exe* (Type Library Importer-Tool).

[Gewusst wie: Registrieren primärer Interop-Assemblys](how-to-register-primary-interop-assemblies.md)  
Beschreibt, wie die primäre Interop-Assemblys zu registrieren, bevor Sie sie in Ihren Projekten verweisen können.

[COM-Interop ohne Registrierung](registration-free-com-interop.md)  
Beschreibt, wie COM-Interop Komponenten ohne Verwendung der Windows-Registrierungs aktivieren kann.

[Gewusst wie: Konfigurieren von .NET Framework-basierten COM-Komponenten für die registrierungsfreie Aktivierung](configure-net-framework-based-com-components-for-reg.md)  
Beschreibt, wie Sie ein Anwendungsmanifest erstellen und das Erstellen und Einbetten eines Komponentenmanifests.
