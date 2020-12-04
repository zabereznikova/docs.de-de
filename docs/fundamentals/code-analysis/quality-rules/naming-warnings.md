---
title: Benennungs Regeln (Code Analyse)
description: Weitere Informationen zu Benennungs Regeln für die Code Analyse.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.namingrules
helpviewer_keywords:
- managed code analysis rules, naming rules
- naming rules
- rules, naming
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 88e7ec6bc1051fa98c46696b2193a5d5912eb111
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590681"
---
# <a name="naming-rules"></a>Benennungsregeln

Benennungs Regeln unterstützen die Einhaltung der Benennungs Konventionen der .net-Entwurfs Richtlinien.

## <a name="in-this-section"></a>In diesem Abschnitt

|Regel|Beschreibung|
|----------|-----------------|
|[CA1700: Enumerationswerte nicht mit "Reserviert" benennen.](ca1700.md)|Bei dieser Regel wird vorausgesetzt, dass Enumerationsmember mit einem Namen, der "reserved" enthält, derzeit nicht verwendet werden, sondern Platzhalter sind, die in einer künftigen Version umbenannt oder entfernt werden sollen. Das Umbenennen oder Entfernen eines Members ist eine unterbrechende Änderung.|
|[CA1707: Bezeichner sollten keine Unterstriche enthalten.](ca1707.md)|Bezeichnernamen dürfen keinen Unterstrich (_) enthalten. Namespaces, Typen, Member und Parameter werden von dieser Regel überprüft.|
|[CA1708: Bezeichner sollten sich nicht nur durch die Groß-/Kleinschreibung unterscheiden.](ca1708.md)|Bezeichner für Namespaces, Typen, Member und Parameter dürfen sich nicht nur durch die Groß-/Kleinschreibung unterscheiden, weil Sprachen, die auf die Common Language Runtime abzielen, nicht zwischen Groß- und Kleinschreibung unterscheiden müssen.|
|[CA1710: Bezeichner sollten ein richtiges Suffix aufweisen.](ca1710.md)|Gemäß der Konvention verfügen die Namen von Typen, die bestimmte Basis Typen erweitern oder bestimmte Schnittstellen oder Typen implementieren, die von diesen Typen abgeleitet sind, über ein Suffix, das dem Basistyp oder der Schnittstelle zugeordnet ist.|
|[CA1711: Bezeichner sollten kein falsches Suffix aufweisen.](ca1711.md)|Nur die Namen von Typen, die bestimmte Basistypen erweitern oder bestimmte Schnittstellen bzw. Typen implementieren, die von diesen Typen abgeleitet werden, sollten stets mit bestimmten reservierten Suffixen enden. Für andere Typnamen sollten diese reservierten Suffixe nicht verwendet werden.|
|[CA1712: Keine Typnamen als Präfixe für Enumerationswerte verwenden.](ca1712.md)|Namen von Enumerationsmembern haben nicht den Typnamen als Präfix, da von den Entwicklungs Tools Typinformationen erwartet werden.|
|[CA1713: Ereignisse sollten kein Before- oder After-Präfix aufweisen.](ca1713.md)|Der Name eines Ereignisses beginnt mit "Before" oder "After". Um verwandte Ereignisse zu benennen, die in einer bestimmten Reihenfolge ausgelöst werden, verwenden Sie die Gegenwarts- oder Vergangenheitsform, um ihre relative Position in der Aktionsfolge anzugeben.|
|[CA1714: Flags-Enumerationen sollten Pluralnamen aufweisen.](ca1714.md)|Eine öffentliche Enumeration weist das System. FlagsAttribute-Attribut auf, und der Name endet nicht mit "s". Typen, die mit FlagsAttribute gekennzeichnet sind, haben Namen, die den Plural aufweisen, da das Attribut angibt, dass mehr als ein Wert angegeben werden kann.|
|[CA1715: Bezeichner sollten ein korrektes Präfix aufweisen.](ca1715.md)|Der Name einer extern sichtbaren Schnittstelle beginnt nicht mit einem Großbuchstaben "I".  Der Name eines generischen Typparameters für einen extern sichtbaren Typ oder eine extern sichtbare Methode beginnt nicht mit dem Großbuchstaben "T".|
|[CA1716: Bezeichner sollten nicht mit Schlüsselwörtern übereinstimmen.](ca1716.md)|Ein Namespacename oder ein Typname stimmt mit einem reservierten Schlüsselwort in einer Programmiersprache überein. Bezeichner für Namespaces und Typen dürfen nicht mit Schlüsselwörtern übereinstimmen, die in Programmiersprachen für die Common Language Runtime definiert sind.|
|[CA1717: Nur FlagsAttribute-Enumerationen sollten Pluralnamen aufweisen.](ca1717.md)|Gemäß den Benennungskonventionen gibt ein Pluralname für eine Enumeration an, dass für die Enumeration mehrere Werte gleichzeitig angegeben werden können.|
|[CA1720: Bezeichner dürfen keine Typnamen enthalten.](ca1720.md)|Der Name eines Parameters in einem extern sichtbaren Member enthält einen Datentypnamen, oder der Name eines extern sichtbaren Members enthält einen sprachspezifischen Datentypnamen.|
|[CA1721: Eigenschaftennamen sollten nicht mit Get-Methoden übereinstimmen.](ca1721.md)|Der Name eines öffentlichen oder geschützten Members beginnt mit "Get" und stimmt in anderer Hinsicht mit dem Namen einer öffentlichen oder geschützten Eigenschaft überein. "Get"-Methoden und -Eigenschaften sollten Namen aufweisen, die ihre Funktionen deutlich erkennbar machen.|
|[CA1724: Typnamen sollten nicht mit Namespaces übereinstimmen.](ca1724.md)|Typnamen sollten nicht mit den Namen von .NET-Namespaces identisch sein. Durch einen Verstoß gegen diese Regel kann die Benutzerfreundlichkeit der Bibliothek reduziert werden.|
|[CA1725: Parameternamen sollten mit der Basisdeklaration übereinstimmen.](ca1725.md)|Die konsistente Benennung von Parametern in einer Überschreibungshierarchie erhöht die Verwendbarkeit von Methodenüberschreibungen. Ein Parametername in einer abgeleiteten Methode, der vom Namen in der Basisdeklaration abweicht, kann zu Unklarheiten dahingehend führen, ob es sich bei der Methode um eine Überschreibung der Basismethode oder eine neue Überladung der Methode handelt.|
