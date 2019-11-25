---
title: Ladealgorithmus für verwaltete Assemblys – .NET Core
description: Beschreibung von Details des Ladealgorithmus für verwaltete Assemblys in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 312a320676be6eb453697e0704ab771a6707618b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973500"
---
# <a name="managed-assembly-loading-algorithm"></a>Ladealgorithmus für verwaltete Assemblys

Verwaltete Assemblys werden in mehreren Schritten über einen Algorithmus gesucht und geladen.

Für alle verwalteten Assemblys – mit Ausnahme von Satellitenassemblys und `WinRT`-Assemblys – wird derselbe Algorithmus verwendet.

## <a name="when-are-managed-assemblies-loaded"></a>Wann werden verwaltete Assemblys geladen?

Das am häufigsten angewandte Verfahren, um das Laden einer verwalteten Assembly auszulösen, ist ein statischer Assemblyverweis. Diese Verweise werden vom Compiler immer dann eingefügt, wenn der Code einen in einer anderen Assembly definierten Typ verwendet. Diese Assemblys werden nach Bedarf von der Runtime geladen (`load-by-name`).

Die direkte Verwendung spezifischer APIs löst das Laden ebenfalls aus:

|API  |BESCHREIBUNG  |`Active` <xref:System.Runtime.Loader.AssemblyLoadContext> |
|---------|---------|---------|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyName%2A?displayProperty=nameWithType>|`Load-by-name`|Die [this](../../csharp/language-reference/keywords/this.md)-Instanz.|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType><p><xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromNativeImagePath%2A?displayProperty=nameWithType>|Aus dem Pfad laden|Die [this](../../csharp/language-reference/keywords/this.md)-Instanz.|
<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromStream%2A?displayProperty=nameWithType>|Aus einem Objekt laden|Die [this](../../csharp/language-reference/keywords/this.md)-Instanz.|
|<xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>|Aus dem Pfad in eine neue <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz laden|Die neue <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz.|
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>|Aus dem Pfad in die <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>-Instanz laden<p>Fügt <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> einen <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving>-Handler hinzu. Der Handler lädt die Abhängigkeiten der Assembly aus dem zugehörigen Verzeichnis.|Die <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>-Instanz.|
|<xref:System.Reflection.Assembly.Load(System.Reflection.AssemblyName)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.String)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>|`Load-by-name`.|Vom Aufrufer abgeleitet.<p>Verwenden Sie bevorzugt <xref:System.Runtime.Loader.AssemblyLoadContext>-Methoden.|
|<xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.Byte[],System.Byte[])?displayProperty=nameWithType>|Aus dem Objekt in eine neue <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz laden|Die neue <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz.|
<xref:System.Type.GetType(System.String)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType>|`Load-by-name`.|Vom Aufrufer abgeleitet.<p>Verwenden Sie bevorzugt <xref:System.Type.GetType%2A?displayProperty=nameWithType>-Methoden mit einem `assemblyResolver`-Argument.|
<xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>|Wenn der Typ-`name` einen von der Assembly qualifizierten generischen Typ beschreibt, wird `Load-by-name` auslöst.|Vom Aufrufer abgeleitet.<p>Bevorzugen Sie <xref:System.Type.GetType%2A?displayProperty=nameWithType>, wenn Sie von der Assembly qualifizierte Typnamen verwenden.|
<xref:System.Activator.CreateInstance(System.String,System.String)?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Object[])?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Boolean,System.Reflection.BindingFlags,System.Reflection.Binder,System.Object[],System.Globalization.CultureInfo,System.Object[])?displayProperty=nameWithType>|`Load-by-name`.|Vom Aufrufer abgeleitet.<p>Verwenden Sie bevorzugt <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>-Methoden, die ein <xref:System.Type>-Argument übernehmen.|

## <a name="algorithm"></a>Algorithmus

Der folgende Algorithmus beschreibt, wie die Runtime eine verwaltete Assembly lädt.

1. Ermitteln Sie den `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.

    - Bei einem statischen Assemblyverweis ist der `active` <xref:System.Runtime.Loader.AssemblyLoadContext> die Instanz, die die verweisende Assembly geladen hat.
    - Bei bevorzugten APIs wird der `active` <xref:System.Runtime.Loader.AssemblyLoadContext> explizit angegeben.
    - Andere APIs leiten den `active` <xref:System.Runtime.Loader.AssemblyLoadContext> ab. Für diese APIs wird die <xref:System.Runtime.Loader.AssemblyLoadContext.CurrentContextualReflectionContext?displayProperty=nameWithType>-Eigenschaft verwendet. Wenn der Wert `null` ist, wird die abgeleitete <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz verwendet.
    - Siehe Tabelle oben.

2. Bei den `Load-by-name`-Methoden lädt der aktive <xref:System.Runtime.Loader.AssemblyLoadContext> die Assembly. Reihenfolge nach Priorität:
    - Überprüfen des `cache-by-name`

    - Aufrufen der <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>-Funktion

    - Überprüfen des Caches der <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>-Instanzen und Ausführen der Logik für die [Standardüberprüfung verwalteter Assemblys](default-probing.md#managed-assembly-default-probing)

    - Auslösen des <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType>-Ereignisses für den aktiven AssemblyLoadContext

    - Auslösen des <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignisses

3. Bei den anderen Ladetypen lädt der `active` <xref:System.Runtime.Loader.AssemblyLoadContext> die Assembly. Reihenfolge nach Priorität:
    - Überprüfen des `cache-by-name`

    - Laden aus dem angegebenen Pfad oder dem unformatierten Assemblyobjekt

4. In beiden Fällen gilt beim Laden einer Assembly Folgendes:
   - Das <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>-Ereignis wird ausgelöst.
   - Dem `cache-by-name` der <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz der Assembly wird ein Verweis hinzugefügt.

5. Wenn die Assembly gefunden wurde, wird dem `cache-by-name` der `active` <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz bei Bedarf ein Verweis hinzugefügt.
