---
title: Erstellen und Verwenden von Assemblys mit starkem Namen
ms.date: 08/19/2019
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, about strong-named assemblies
- strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, scenarios
- assemblies [.NET Framework], strong-named
- strong-named assemblies, loading into trusted application domains
- assembly binding, strong-named
ms.assetid: ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9
ms.openlocfilehash: 18a0b7d657290835a34c705513d0d7a4ccbfc61c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75738681"
---
# <a name="create-and-use-strong-named-assemblies"></a>Erstellen und Verwenden von Assemblys mit starkem Namen

Ein starker Name setzt sich aus der Identität der Assembly – dem einfachen Textnamen, der Versionsnummer und Kulturinformationen (falls vorhanden) – sowie einem öffentlichen Schlüssel und einer digitalen Signatur zusammen. Er wird mithilfe des entsprechenden privaten Schlüssels aus einer Assemblydatei generiert. (Die Assemblydatei enthält das Assemblymanifest, das wiederum die Namen und Hashes aller Dateien enthält, die die Assembly bilden.)

> [!WARNING]
> Verlassen Sie sich für die Sicherheit nicht auf starke Namen. Diese Namen bieten lediglich eine eindeutige Identität.

Eine Assembly mit starkem Namen kann nur Typen aus anderen Assemblys mit starkem Namen verwenden. Andernfalls ist die Integrität der Assembly mit starkem Namen beeinträchtigt.

> [!NOTE]
> .NET Core unterstützt Assemblys mit starkem Namen, und alle Assemblys in der .NET Core-Bibliothek sind signiert. Für die meisten Assemblys von Drittanbietern sind jedoch keine starken Namen erforderlich. Weitere Informationen finden Sie unter [Strong Name Signing (Signieren von Assemblys mit starkem Namen)](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) auf GitHub.

## <a name="strong-name-scenario"></a>Szenario für starken Namen

Im folgenden Szenario wird kurz umrissen, wie eine Assembly mit einem starken Namen signiert und wie später mit diesem Namen auf sie verwiesen wird.

1. Assembly A wird auf eine der folgenden Weisen mit einem starken Namen erstellt:

    - Durch Verwenden einer Entwicklungsumgebung, die das Erstellen starker Namen unterstützt, wie z.B. Visual Studio.

    - Durch Erstellen eines kryptografischen Schlüsselpaars mithilfe des [Strong Name-Tools (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) und Zuweisen dieses Schlüsselpaars zur Assembly unter Verwendung eines Befehlszeilencompilers oder mit dem [Assemblylinker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md). Das Windows SDK stellt sowohl „Sn“.exe als auch „Al.exe“ zur Verfügung.

2. Die Entwicklungsumgebung oder das Tool signiert den Hash der Datei, die das Assemblymanifest enthält, mit dem privaten Schlüssel des Entwicklers. Diese digitale Signatur wird in der PE (Portable Executable)-Datei gespeichert, die das Manifest von Assembly A enthält.

3. Assembly B ist ein Consumer von Assembly A. Der Referenzabschnitt des Manifests von Assembly B enthält ein Token, das den öffentlichen Schlüssel von Assembly A darstellt. Ein Token ist ein Teilabschnitt des vollständigen öffentlichen Schlüssels und wird aus Platzgründen oft an Stelle des eigentlichen Schlüssels verwendet.

4. Die Common Language Runtime überprüft die starke Namenssignatur, wenn die Assembly im globalen Assemblycache platziert wird. Beim Binden mit starken Namen zur Runtime vergleicht die Common Language Runtime den im Manifest von Assembly B gespeicherten Schlüssel mit dem Schlüssel, der verwendet wurde, um den starken Namen von Assembly A zu generieren. Wenn die Sicherheitstests von .NET Framework durchlaufen und die Bindung abgeschlossen wurde, garantiert Assembly B, dass Bits von Assembly A nicht verändert wurden, und dass sie tatsächlich von den Entwicklern von Assembly A stammen.

> [!NOTE]
> Dieses Szenario löst keine Vertrauenswürdigkeitsprobleme. Assemblys können neben starken Namen auch vollständige Microsoft Authenticode-Signaturen tragen. Authenticode-Signaturen enthalten ein Zertifikat, das Vertrauenswürdigkeit bescheinigt. Beachten Sie unbedingt, dass bei starken Namen nicht erforderlich ist, Code auf diese Weise zu signieren. Starke Namen bieten lediglich eine eindeutige Identität.

## <a name="bypass-signature-verification-of-trusted-assemblies"></a>Umgehen der Signaturüberprüfung für vertrauenswürdige Assemblys

Ab NET Framework 3.5 Service Pack 1 werden Signaturen mit starkem Namen nicht überprüft, wenn ein Assembly in eine vollständig vertrauenswürdige Anwendungsdomäne geladen wird, wie etwa die Standardanwendungsdomäne für die Zone `MyComputer`. Dies wird Strong-Name-Bypass-Feature genannt. In einer vollständig vertrauenswürdigen Umgebung sind Forderungen nach <xref:System.Security.Permissions.StrongNameIdentityPermission> für signierte, vollständig vertrauenswürdige Assemblys immer erfolgreich, unabhängig von deren Signatur. Das Strong-Name-Bypass-Feature vermeidet in dieser Situation den Aufwand der Überprüfung der Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys. Dies ermöglicht ein schnelleres Laden der Assemblys.

Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:

- Voll vertrauenswürdig ohne <xref:System.Security.Policy.StrongName>-Beweis (hat z. B. `MyComputer`-Zonenbeweis)

- Geladen in eine voll vertrauenswürdige <xref:System.AppDomain>

- Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain>

- Nicht verzögert signiert

Diese Funktion kann für einzelne Anwendungen oder einen Computer deaktiviert werden. Weitere Informationen finden Sie unter [How to: Deaktivieren des Features zur Umgehung von starken Namen](disable-strong-name-bypass-feature.md).

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[How to: Erstellen eines öffentlichen/privaten Schlüsselpaars](create-public-private-key-pair.md)|Beschreibt das Erstellen eines kryptografischen Schlüsselpaars zum Signieren einer Assembly.|
|[How to: Signieren einer Assembly mit einem starken Namen](sign-strong-name.md)|Beschreibt das Erstellen einer Assembly mit starkem Namen.|
|[Verbesserte starke Namen](enhanced-strong-naming.md)|Beschreibt Erweiterungen der starken Namen in .NET Framework 4.5.|
|[How to: Verweisen auf eine Assembly mit starkem Namen](reference-strong-named.md)|Beschreibt, wie auf Typen oder Ressourcen in einer Assembly mit starkem Namen zur Kompilier- oder Laufzeit verwiesen wird.|
|[How to: Deaktivieren des Features zur Umgehung von starken Namen](disable-strong-name-bypass-feature.md)|Beschreibt, wie die Funktion, die die Validierung von Signaturen mit starkem Namen umgeht, deaktiviert wird. Diese Funktion kann für alle oder bestimmte Anwendungen deaktiviert werden.|
|[Erstellen von Assemblys](create.md)|Bietet eine Übersicht über Einfach- und Mehrfachdateiassemblys.|
|[Verzögern der Signierung einer Assembly in Visual Studio](/visualstudio/ide/managing-assembly-and-manifest-signing#how-to-sign-an-assembly-in-visual-studio)|Erläutert das Signieren einer Assembly mit einem starken Namen nach dem Erstellen der Assembly.|
|[Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md)|Beschreibt das Tool, das in .NET Framework enthalten ist, mit dem Assemblys mit starken Namen erstellt werden können. Dieses Tool stellt Optionen zum Verwalten von Schlüsseln, Erzeugen und Überprüfen von Signaturen bereit.|
|[Al.exe (Assembly Linker-Tool)](../../framework/tools/al-exe-assembly-linker.md)|Beschreibt das Tool, das in .NET Framework enthalten ist, mit dem eine Datei generiert wird, die ein Assemblymanifest von Modulen oder Ressourcendateien besitzt.|
