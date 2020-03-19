---
title: Ladealgorithmus für Satellitenassemblys – .NET Core
description: Beschreibung von Details des Ladealgorithmus für Satellitenassemblys in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: bfdc1d8179d46a13b3d137a87397fa3e573da33c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72303623"
---
# <a name="satellite-assembly-loading-algorithm"></a>Ladealgorithmus für Satellitenassemblys

Satellitenassemblys werden verwendet, um lokalisierte Ressourcen für Sprachen und Kulturen zu speichern.

Für Satellitenassemblys wird ein anderer Ladealgorithmus als für allgemeine verwaltete Assemblys verwendet.

## <a name="when-are-satellite-assemblies-loaded"></a>Wann werden Satellitenassemblys geladen?

Satellitenassemblys werden beim Laden einer lokalisierten Ressource geladen.

Die grundlegende API zum Laden lokalisierter Ressourcen ist die <xref:System.Resources.ResourceManager?displayProperty=fullName>-Klasse. Letztendlich ruft die <xref:System.Resources.ResourceManager>-Klasse die <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A>-Methode für jede <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> auf.

APIs auf höherer Ebene können eine API auf niedrigerer Ebene abstrahieren.

## <a name="algorithm"></a>Algorithmus

Der .NET Core-Ressourcenfallbackprozess besteht aus folgenden Schritten:

1. Bestimmen Sie die `active` <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz. In allen Fällen handelt es sich bei der `active`-Instanz um den <xref:System.Runtime.Loader.AssemblyLoadContext> der ausführenden Assembly.

2. Die `active`-Instanz versucht, eine Satellitenassembly für die angeforderte Kultur in folgender Reihenfolge nach Priorität zu laden:
    - Überprüfen des Caches
    - Überprüfen des Verzeichnisses der aktuell ausgeführten Assembly auf ein Unterverzeichnis, das der angeforderten <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> entspricht (z. B. `es-MX`)

        > [!NOTE]
        > Diese Funktion wurde erst ab .NET Core 3.0 implementiert.
        >
        > [!NOTE]
        > Unter Linux und macOS muss beim Unterverzeichnis die Groß-/Kleinschreibung beachtet werden, und eine der folgenden Voraussetzungen muss erfüllt sein:
        > - Die Groß-/Kleinschreibung muss genau übereinstimmen.
        > - Es wurden nur Kleinbuchstaben verwendet.

    - Wenn `active` die <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>-Instanz ist, durch Ausführen der Logik für [Standardüberprüfungen von Satellitenassemblys (Ressourcen) ](default-probing.md#satellite-resource-assembly-probing).

    - Aufrufen der <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>-Funktion

    - Auslösen des <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType>-Ereignisses

    - Auslösen des <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignisses

3. Wenn eine Satellitenassembly geladen wird:
   - Das <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>-Ereignis wird ausgelöst.
   - Die Assembly wird nach der angeforderten Ressource durchsucht. Wenn die Runtime die Ressource in der Assembly findet, verwendet sie diese. Wenn sie die Ressource nicht findet, fährt sie mit der Suche fort.

    > [!NOTE]
    > Um eine Ressource in der Satellitenassembly zu finden, sucht die Runtime nach der Ressourcendatei, die vom <xref:System.Resources.ResourceManager> für den aktuellen <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> angefordert wird. Sie sucht in der Ressourcendatei nach dem angeforderten Ressourcennamen. Wenn keins von beiden gefunden wird, wird die Ressource als nicht gefunden behandelt.

4. Als Nächstes sucht die Runtime die Assemblys der übergeordneten Kultur über viele mögliche Ebenen hinweg, wobei jedes Mal die Schritte 2 und 3 wiederholt werden.

    Jeder Kultur hat genau ein übergeordnetes Element, das von der <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>-Eigenschaft definiert wird.

    Die Suche nach übergeordneten Kulturen ist beendet, wenn die <xref:System.Globalization.CultureInfo.Parent%2A>-Eigenschaft einer Kultur <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType> ist.

    Für die <xref:System.Globalization.CultureInfo.InvariantCulture> werden die Schritte 2 und 3 nicht wiederholt, sondern stattdessen mit Schritt 5 fortgefahren.

5. Wenn die Ressource immer noch nicht gefunden wurde, wird die Ressource für die Standardkultur (Fallback) verwendet.

   Für gewöhnlich werden die Ressourcen der Standardkultur in die Hauptassembly der Anwendung integriert. Sie können jedoch <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> für die <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType>-Eigenschaft angeben. Dieser Wert gibt an, dass der endgültige Fallbackort für Ressourcen eine Satellitenassembly ist und nicht die Hauptassembly.

    > [!NOTE]
    > Die Standardkultur wird als endgültiges Fallback verwendet. Daher wird empfohlen, immer einen umfassenden Satz an Ressourcen in die Standardressourcendatei zu integrieren. So werden Ausnahmen verhindert. Über diesen umfassenden Satz stellen Sie einen Fallback für alle Ressourcen bereit und stellen sicher, dass immer mindestens eine Ressource für den Benutzer verfügbar ist, auch wenn diese nicht kulturspezifisch ist.

6. Zum Schluss:
   - Wenn die Runtime keine Ressourcendatei für eine Standardkultur (Fallback) findet, wird eine <xref:System.Resources.MissingManifestResourceException> oder <xref:System.Resources.MissingSatelliteAssemblyException> ausgelöst.
   - Wenn die Ressourcendatei gefunden wurde, aber die angeforderte Ressource nicht vorhanden ist, gibt die Anforderung `null` zurück.
