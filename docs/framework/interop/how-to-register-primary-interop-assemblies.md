---
title: 'Vorgehensweise: Registrieren primärer Interop-Assemblys'
description: Registrieren Sie primäre Interopassemblys mit dem Assembly Registration-Tool (Regasm.exe), und informieren Sie sich über andere Aspekte im Zusammenhang mit Interopassemblys.
ms.date: 03/30/2017
helpviewer_keywords:
- registering primary interop assemblies
- primary interop assemblies, registering
ms.assetid: 4b2fcf8a-429d-43ce-8334-e026040be8bb
ms.openlocfilehash: a15bda7b40f160b31028c62cf7c73bdedd9541fa
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622743"
---
# <a name="how-to-register-primary-interop-assemblies"></a>Vorgehensweise: Registrieren primärer Interop-Assemblys

Klassen können nur durch COM-Interop gemarshallt werden und werden immer als Schnittstellen gemarshallt. In einigen Fällen wird die zum Marshallen der Klasse verwendete Schnittstelle als Klassenschnittstelle bezeichnet. Informationen zum Überschreiben der Klassenschnittstelle mit einer beliebigen Schnittstelle finden Sie unter [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md).

 Obwohl jeder Entwickler, der COM-Typen aus einer .NET Framework-Anwendung verwenden möchte, eine interop-Assembly generieren kann, führt dies zu einem Problem. Jedes Mal, wenn ein Entwickler eine COM-Typbibliothek importiert und signiert, erstellt dieser Entwickler einen Satz eindeutiger Typen, die nicht mit denen kompatibel sind, die ein anderer Entwickler importiert und signiert hat. Die Lösung des Typinkompatibilitätsproblems besteht für jeden Entwickler darin, die vom Anbieter bereitgestellte und signierte primäre Interop-Assembly abzurufen.

 Wenn Sie Drittanbieter-COM-Typen für andere Anwendungen verfügbar machen möchten, verwenden Sie immer die primäre Interop-Assembly, die von demselben Herausgeber bereitgestellt wird wie die Typbibliothek, die sie definiert. Zusätzlich zur Bereitstellung garantierter Typkompatibilität werden primäre Interop-Assemblys vom Anbieter häufig angepasst, um die Interoperabilität zu verbessern.

 Selbst wenn Sie nicht beabsichtigen, die COM-Typen von Drittanbietern verfügbar zu machen, lässt sich durch Verwenden der primären Interop-Assembly das Interoperieren mit COM-Komponenten vereinfachen. Diese Strategie bietet jedoch keinen Schutz vor Änderungen, die ein Anbieter an Typen vornehmen kann, die in einer primären Interop-Assembly definiert sind. Wenn Ihre Anwendung einen solchen Schutz erfordert, generieren Sie Ihre eigene Interop-Assembly, anstatt die primäre Interop-Assembly zu verwenden.

 Sie müssen alle erworbenen primären Interop-Assemblys auf dem Entwicklungscomputer registrieren, bevor Sie mit Visual Studio auf sie verweisen können. Visual Studio sucht nach einer primären Interop-Assembly und verwendet diese, wenn Sie zum ersten Mal auf einen Typ aus einer COM-Typbibliothek verweisen. Wenn Visual Studio die der Typbibliothek zugeordnete primäre Interop-Assembly nicht finden kann, werden Sie aufgefordert, diese zu erwerben oder stattdessen eine Interop-Assembly zu erstellen. In gleicher Weise verwendet auch das [Type Library Importer-Tool (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) die Registrierung, um nach primären Interop-Assemblys zu suchen.

 Obwohl eine Registrierung von primären Interop-Assemblys nur dann erforderlich ist, wenn Sie Visual Studio verwenden möchten, bietet eine Registrierung zwei Vorteile:

- Eine registrierte primäre Interop-Assembly ist eindeutig unter dem Registrierungsschlüssel der ursprünglichen Typbibliothek gekennzeichnet. Die Registrierung ist die beste Möglichkeit für Sie, nach einer primären Interop-Assembly auf dem Computer zu suchen.

- Sie können vermeiden, versehentlich eine neue Interop-Assembly zu generieren und zu verwenden, wenn Sie irgendwann in der Zukunft Visual Studio verwenden, um auf einen Typ zu verweisen, für den Sie eine nicht registrierte primäre Interop-Assembly haben.

Verwenden Sie das [Assembly Registration-Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md), um eine primäre Interop-Assembly zu registrieren.

## <a name="to-register-a-primary-interop-assembly"></a>So registrieren Sie eine primäre Interop-Assembly

1. Geben Sie an der Eingabeaufforderung Folgendes ein:

     **regasm** *Assemblyname*

     In diesem Befehl ist *assemblyname* der Dateiname der Assembly, die registriert wird. "Regasm.exe" fügt einen Eintrag für die primäre Interop-Assembly unter dem Registrierungsschlüssel hinzu, unter dem sich auch der Eintrag der ursprünglichen Typbibliothek befindet.

## <a name="example"></a>Beispiel
 Im folgenden Beispiel wird die primäre Interop-Assembly `CompanyA.UtilLib.dll` registriert.

```console
regasm CompanyA.UtilLib.dll
```

## <a name="see-also"></a>Siehe auch

- [Programming with Primary Interop Assemblies (Programmieren mit primären Interop-Assemblys)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/baxfadst(v=vs.100))
- [Suchen primärer Interop-Assemblys](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/y06sxw56(v=vs.100))
- [Verteilen primärer Interop-Assemblys](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w0dt2w20(v=vs.100))
