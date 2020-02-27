---
title: Arten von Breaking Changes
description: Erfahren Sie, wie .NET Core versucht, die Kompatibilität für Entwickler für alle .NET-Versionen zu gewährleisten und welche Änderung als Breaking Change angesehen wird.
ms.date: 06/10/2019
ms.openlocfilehash: bf0cc35d69e6bb501640455604a99a1f48962c4a
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628591"
---
# <a name="changes-that-affect-compatibility"></a>Änderungen, die sich auf die Kompatibilität auswirken

Im Laufe seines Bestehens hat .NET versucht, ein hohes Maß an Kompatibilität von Version zu Version und zwischen den verschiedenen Varianten von.NET aufrechtzuerhalten. Dies gilt auch für .NET Core. Obwohl .NET Core als eine von .NET Framework unabhängige neue Technologie betrachtet werden kann, schränken zwei wesentliche Faktoren die Möglichkeit von .NET Core ein, von .NET Framework abzuweichen:

- Eine große Anzahl von Entwicklern hat entweder ursprünglich .NET Framework-Anwendungen entwickelt oder entwickelt diese weiterhin. Sie erwarten ein konsistentes Verhalten in .NET-Implementierungen.

- .NET Standard-Bibliotheksprojekte ermöglichen es Entwicklern, Bibliotheken zu erstellen, die auf gemeinsame APIs ausgerichtet sind, die von .NET Core und.NET Framework gemeinsam genutzt werden. Entwickler erwarten, dass sich eine in einer .NET Core-Anwendung verwendete Bibliothek genauso verhält, wie dieselbe Bibliothek, die in einer .NET Framework-Anwendung verwendet wird.

Neben der Kompatibilität zwischen .NET-Implementierungen erwarten Entwickler ein hohes Maß an Kompatibilität zwischen .NET Core-Versionen. Insbesondere sollte Code, der für eine frühere Version von .NET Core geschrieben wurde, problemlos auf einer späteren Version von .NET Core ausgeführt werden können. Tatsächlich erwarten viele Entwickler, dass die neuen APIs in den neu veröffentlichten Versionen von .NET Core auch mit den Vorabversionen kompatibel sein sollten, in denen diese APIs eingeführt wurden.

Dieser Artikel beschreibt die Kategorien von Kompatibilitätsänderungen (oder Breaking Changes) und die Art und Weise, wie das .NET-Team Änderungen in jeder dieser Kategorien bewertet. Zu verstehen, wie das .NET-Team mit möglichen Breaking Changes umgeht, ist besonders hilfreich für Entwickler, die Pull Requests im GitHub-Repository [dotnet/runtime](https://github.com/dotnet/runtime) öffnen, das das Verhalten bestehender APIs ändert.

> [!NOTE]
> Eine Definition von Kompatibilitätskategorien, wie z.B. Binärkompatibilität und Abwärtskompatibilität, finden Sie unter [Breaking Change-Kategorien](categories.md).

In den folgenden Abschnitten werden die Kategorien der Änderungen an den .NET Core-APIs und deren Auswirkungen auf die Anwendungskompatibilität beschrieben. Änderungen sind zulässig ✔️, nicht zulässig ❌, oder es muss beurteilt und bewertet werden, wie vorhersehbar, offensichtlich und konsistent das bisherige Verhalten war ❓.

> [!NOTE]
> Bibliotheksentwickler können diese Kriterien nicht nur als Leitfaden für die Bewertung von Änderungen an .NET Core-Bibliotheken verwenden, sondern auch für die Bewertung von Änderungen an ihren Bibliotheken, die auf mehrere .NET-Implementierungen und -Versionen ausgerichtet sind.

## <a name="modifications-to-the-public-contract"></a>Änderungen am öffentlichen Vertrag

Änderungen in dieser Kategorie modifizieren die öffentliche Oberfläche eines Typs. Die meisten Änderungen in dieser Kategorie sind unzulässig, da sie die *Abwärtskompatibilität* verletzen (die Fähigkeit einer Anwendung, die mit einer früheren Version einer API entwickelt wurde, ohne Neukompilierung auf einer späteren Version ausgeführt zu werden).

### <a name="types"></a>Typen

- ✔️ **ZULÄSSIG: Entfernen einer Schnittstellenimplementierung aus einem Typ, wenn die Schnittstelle bereits durch einen Basistyp implementiert ist**

- ❓ **ERFORDERT BEURTEILUNG: Hinzufügen einer neuen Schnittstellenimplementierung zu einem Typ**

  Dies ist eine zulässige Änderung, da sie bestehende Clients nicht beeinträchtigt. Jede Änderung des Typs muss innerhalb der hier definierten Grenzen für zulässige Änderungen erfolgen, damit die neue Implementierung weiterhin zulässig ist. Extreme Vorsicht ist geboten, wenn Schnittstellen hinzugefügt werden, die die Fähigkeit eines Designers oder Serialisierungsmoduls direkt beeinflussen, Code oder Daten zu generieren, die nicht auf unteren Ebenen verwendet werden können. Ein Beispiel ist die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle.

- ❓ **ERFORDERT BEURTEILUNG: Einführen einer neuen Basisklasse**

  Ein Typ kann in einer Hierarchie zwischen zwei bestehenden Typen eingefügt werden, wenn er keinen neuen [abstract](../../csharp/language-reference/keywords/abstract.md)-Member einführt oder die Semantik oder das Verhalten bestehender Typen ändert. So wurde beispielsweise in .NET Framework 2.0 die Klasse <xref:System.Data.Common.DbConnection> zu einer neuen Basisklasse für <xref:System.Data.SqlClient.SqlConnection>, die zuvor direkt von <xref:System.ComponentModel.Component> abgeleitet wurde.

- ✔️ **ZULÄSSIG: Verschieben eines Typs von einer Assembly zu einer anderen**

  Die *alte* Assembly muss mit dem <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> markiert werden muss, das auf die neue Assembly verweist.

- ✔️ **ZULÄSSIG: Ändern des Typs [struct](../../csharp/language-reference/builtin-types/struct.md) in einen Typ `readonly struct`**

  Ein `readonly struct`-Typ darf nicht in einen `struct`-Typ geändert werden.

- ✔️ **ZULÄSSIG: Hinzufügen des Schlüsselworts [sealed](../../csharp/language-reference/keywords/sealed.md) oder [abstract](../../csharp/language-reference/keywords/abstract.md) zu einem Typ, wenn keine *zugänglichen* (öffentlichen oder geschützten) Konstruktoren vorhanden sind**

- ✔️ **ZULÄSSIG: Erweitern der Sichtbarkeit eines Typs**

- ❌ **NICHT ZULÄSSIG: Ändern des Namespace oder des Namens eines Typs**

- ❌ **NICHT ZULÄSSIG: Umbenennen oder Entfernen eines öffentlichen Typs**

   Dies unterbricht sämtlichen Code, der den umbenannten oder entfernten Typen verwendet.

- ❌ **NICHT ZULÄSSIG: Ändern des einer Enumeration zugrunde liegenden Typs**

   Dies ist ein Breaking Change der Kompilierzeit und des Verhaltens und darüber hinaus ein binärer Breaking Change, durch die die Analyse der Attributargumente unterbunden werden könnte.

- ❌ **NICHT ZULÄSSIG: Versiegeln eines bisher nicht versiegelten Typs**

- ❌ **NICHT ZULÄSSIG: Hinzufügen einer Schnittstelle zur Menge der Basistypen einer Schnittstelle**

   Wenn ein Schnittstelle eine Schnittstelle implementiert, die sie zuvor nicht implementiert hat, werden alle Typen, die die ursprüngliche Version der Schnittstelle implementiert haben, beschädigt.

- ❓ **ERFORDERT BEURTEILUNG: Entfernen eine Klasse aus der Menge der Basisklassen oder einer Schnittstelle aus der Menge der implementierten Schnittstellen**

  Es gibt eine Ausnahme von der Regel zur Entfernung von Schnittstellen: Sie können die Implementierung einer Schnittstelle hinzufügen, die aus der entfernten Schnittstelle abgeleitet ist. Sie können beispielsweise <xref:System.IDisposable> entfernen, wenn der Typ oder die Schnittstelle nun <xref:System.ComponentModel.IComponent> implementiert, wodurch <xref:System.IDisposable> implementiert wird.

- ❌ **NICHT ZULÄSSIG: Ändern eines `readonly struct`-Typs in einen [struct](../../csharp/language-reference/builtin-types/struct.md)-Typ**

  Ein `struct`-Typ darf nicht in einen `readonly struct`-Typ geändert werden.

- ❌ **NICHT ZULÄSSIG: Ändern eines [struct](../../csharp/language-reference/builtin-types/struct.md)-Typs in einen `ref struct`-Typ (und umgekehrt)**

- ❌ **NICHT ZULÄSSIG: Reduzieren der Sichtbarkeit eines Typs**

   Die Sichtbarkeit eines Typs darf jedoch erhöht werden.

### <a name="members"></a>Member

- ✔️ **ZULÄSSIG: Erweitern der Sichtbarkeit eines nicht [virtuellen](../../csharp/language-reference/keywords/sealed.md) Members**

- ✔️ **ZULÄSSIG: Hinzufügen eines abstrakten Members zu einem öffentlichen Typ, der keine *zugänglichen* (öffentlichen oder geschützten) Konstruktoren hat, oder wenn der Typ [versiegelt](../../csharp/language-reference/keywords/sealed.md) ist**

  Das Hinzufügen eines abstrakten-Members zu einem Typ mit zugänglichen (öffentlichen oder geschützten) Konstruktoren, der nicht `sealed` ist, ist zulässig.

- ✔️ **ZULÄSSIG: Einschränken der Sichtbarkeit eines [geschützten](../../csharp/language-reference/keywords/protected.md) Members, wenn der Typ keine zugänglichen (öffentlichen oder geschützten) Konstruktoren hat, oder wenn der Typ [versiegelt](../../csharp/language-reference/keywords/sealed.md) ist**

- ✔️ **ZULÄSSIG: Verschieben eines Members in eine Klasse, die in der Hierarchie höher liegt als der Typ, aus dem er entfernt wurde**

- ✔️ **ZULÄSSIG: Hinzufügen oder Entfernen einer Außerkraftsetzung**

  Die Einführung einer Außerkraftsetzung kann dazu führen, dass vorherige Consumer beim Aufrufen von [base](../../csharp/language-reference/keywords/base.md) die Außerkraftsetzung überspringen.

- ✔️ **ZULÄSSIG: Hinzufügen eines Konstruktors zu einer Klasse, gemeinsam mit einem Konstruktor (ohne Parameter), wenn die Klasse zuvor keine Konstruktoren hatte**

   Das Hinzufügen eines Konstruktors zu einer Klasse, die bisher keine Konstruktoren hatte, *ohne* den parameterlosen Konstruktor hinzuzufügen, ist jedoch nicht zulässig.

- ✔️ **ZULÄSSIG: Ändern eines Members von [abstrakt](../../csharp/language-reference/keywords/abstract.md) zu [virtuell](../../csharp/language-reference/keywords/virtual.md)**

- ✔️ **ZULÄSSIG: Wechseln von einem `ref readonly`- zu einem `ref`-Rückgabewert (mit Ausnahme von virtuellen Methoden oder Schnittstellen)**

- ✔️ **ZULÄSSIG: Entfernen von [readonly](../../csharp/language-reference/keywords/readonly.md) aus einem Feld, es sei denn, der statische Typ des Felds ist ein veränderlicher Werttyp**

- ✔️ **ZULÄSSIG: Aufrufen eines bisher noch nicht definierten neuen Ereignisses**

- ❓ **ERFORDERT BEURTEILUNG: Hinzufügen eines neuen Instanzenfelds zu einem Typ**

   Diese Änderung wirkt sich auf die Serialisierung aus.

- ❌ **NICHT ZULÄSSIG: Umbenennen oder Entfernen eines öffentlichen Members oder Parameters**

   Dies unterbricht sämtlichen Code, der den umbenannten oder entfernten Member oder Parameter verwendet.

   Dazu gehört auch das Entfernen oder Umbenennen eines Getters oder Setters aus einer Eigenschaft sowie das Umbenennen oder Entfernen von Enumerationsmembern.

- ❌ **NICHT ZULÄSSIG: Hinzufügen eines Members zu einer Schnittstelle**

- ❌ **NICHT ZULÄSSIG: Ändern des Werts einer öffentlichen Konstante oder des Enumerationsmembers**

- ❌ **NICHT ZULÄSSIG: Ändern des Typs einer Eigenschaft, eines Felds, eines Parameters oder eines Rückgabewerts**

- ❌ **NICHT ZULÄSSIG: Hinzufügen, Entfernen oder Ändern der Reihenfolge von Parametern**

- ❌ **NICHT ZULÄSSIG: Hinzufügen oder Entfernen der Schlüsselwörter [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) oder [ref](../../csharp/language-reference/keywords/ref.md) zu oder aus einem Parameter**

- ❌ **NICHT ZULÄSSIG: Umbenennen eines Parameters (einschließlich der Änderung der Groß-/Kleinbuchschreibung)**

  Dies gilt aus zwei Gründen als Unterbrechung:

  - Damit werden spät gebundene Szenarien wie die späte Bindungsfunktion in Visual Basic und [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) in C# unterbrochen.

  - Es unterbricht die [Quellenkompatibilität](categories.md#source-compatibility), wenn Entwickler [benannte Argumente](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments) verwenden.

- ❌ **NICHT ZULÄSSIG: Wechseln von einem `ref`- zu einem `ref readonly`-Rückgabewert**

- ❌️ **NICHT ZULÄSSIG: Wechseln von einem `ref readonly`- zu einem `ref`-Rückgabewert bei einer virtuellen Methode oder Schnittstelle**

- ❌ **NICHT ZULÄSSIG: Hinzufügen oder Entfernen von [abstract](../../csharp/language-reference/keywords/abstract.md) zu oder aus einem Member**

- ❌ **NICHT ZULÄSSIG: Entfernen des Schlüsselworts [virtual](../../csharp/language-reference/keywords/virtual.md) aus einem Member**

  Obwohl dies oft keinen Breaking Change darstellt, da der C#-Compiler dazu tendiert, zum Aufrufen nicht virtueller Methoden Intermediate Language (IL)-Anweisungen [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) auszugeben (`callvirt` führt eine Prüfung auf NULL durch, was bei einem normalen Aufruf nicht der Fall ist), ist dieses Verhalten aus verschiedenen Gründe nicht unveränderlich:
  - C# ist nicht die einzige Sprache, auf die .NET ausgerichtet ist.

  - Der C#-Compiler versucht zunehmend, `callvirt` für einen normalen Aufruf zu optimieren, wenn die Zielmethode nicht virtuell und wahrscheinlich nicht Null ist (z.B. eine Methode, auf die über den [NULL-bedingten Operator „?“](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-) zugegriffen wird).

  Aus einer Methode eine virtuelle Methode zu machen bedeutet, dass der Consumercode sie oft nicht virtuell aufruft.

- ❌ **NICHT ZULÄSSIG: Hinzufügen des Schlüsselworts[ virtual](../../csharp/language-reference/keywords/virtual.md) zu einem Member**

- ❌ **NICHT ZULÄSSIG: Umwandeln eines virtuellen Members in einen abstrakten Member**

  Ein [virtueller Member](../../csharp/language-reference/keywords/virtual.md) stellt eine Methodenimplementierung bereit, die von einer abgeleiteten Klasse außer Kraft gesetzt werden *kann*. Ein [abstrakter Member](../../csharp/language-reference/keywords/abstract.md) stellt keine Implementierung bereit und *muss* außer Kraft gesetzt werden.

- ❌ **NICHT ZULÄSSIG: Hinzufügen eines abstrakten-Members zu einem öffentlichen Typ mit zugänglichen (öffentlichen oder geschützten) Konstruktoren, der nicht [versiegelt](../../csharp/language-reference/keywords/sealed.md) ist**

- ❌ **NICHT ZULÄSSIG: Hinzufügen oder Entfernen des Schlüsselworts [static](../../csharp/language-reference/keywords/static.md) zu oder aus einem Member**

- ❌ **NICHT ZULÄSSIG: Hinzufügen einer Überladung, die eine vorhandene Überladung ausschließt und ein anderes Verhalten definiert**

  Dies unterbricht vorhandene Clients, die an die vorherige Überladung gebunden waren. Wenn eine Klasse beispielsweise eine einzelne Version einer Methode hat, die <xref:System.UInt32> akzeptiert, wird ein vorhandener Consumer erfolgreich an diese Überladung gebunden, wenn ein <xref:System.Int32>-Wert übergeben wird. Wenn Sie jedoch eine Überladung hinzufügen, die <xref:System.Int32> akzeptiert, bindet sich der Compiler beim Neukompilieren oder beim Verwenden der späten Bindung an die neue Überladung. Wenn dies ein anderes Verhalten zur Folge hat, ist dies ein Breaking Change.

- ❌ **NICHT ZULÄSSIG: Hinzufügen eines Konstruktors zu einer Klasse, die bisher keine Konstruktoren hatte, ohne den parameterlosen Konstruktor hinzuzufügen**

- ❌️ **NICHT ZULÄSSIG: Hinzufügen von [readonly](../../csharp/language-reference/keywords/readonly.md) zu einem Feld**

- ❌ **NICHT ZULÄSSIG: Reduzieren der Sichtbarkeit eines Members**

   Dazu gehört das Reduzieren der Sichtbarkeit eines [geschützten](../../csharp/language-reference/keywords/protected.md) Members, wenn *zugängliche* (`public` oder `protected`) Konstruktoren vorhanden sind und der Typ *nicht* [versiegelt](../../csharp/language-reference/keywords/sealed.md) ist. Wenn dies nicht der Fall ist, ist das Reduzieren der Sichtbarkeit eines geschützten Members zulässig.

   Die Sichtbarkeit eines Members darf erhöht werden.

- ❌ **NICHT ZULÄSSIG: Ändern des Typs eines Members**

   Der Rückgabewert einer Methode oder der Typ einer Eigenschaft oder eines Feldes kann nicht geändert werden. So kann beispielsweise die Signatur einer Methode, die ein <xref:System.Object> zurückgibt, nicht geändert werden, um ein <xref:System.String> zurückzugeben, oder umgekehrt.

- ❌ **NICHT ZULÄSSIG: Hinzufügen eines Felds zu einer Struktur, die bisher keinen Status hatte**

  Definitive Zuweisungsregeln erlauben die Verwendung von nicht initialisierten Variablen, sofern der Variablentyp eine zustandslose Struktur ist. Wenn die Struktur zustandsbehaftet gemacht wird, könnte der Code nicht initialisierte Daten erhalten. Dies ist möglicherweise sowohl ein Quell-Breaking Change als auch ein binärer Breaking Change.

- ❌ **NICHT ZULÄSSIG: Auslösen eines vorhandenen Ereignisses, das bisher noch nicht ausgelöst wurde**

## <a name="behavioral-changes"></a>Verhaltensänderung

### <a name="assemblies"></a>Assemblys

- ✔️ **ZULÄSSIG: Übertragbarmachen einer Assembly, wenn dieselben Plattformen weiterhin unterstützt werden**

- ❌ **NICHT ZULÄSSIG: Ändern des Namens einer Assembly**
- ❌ **NICHT ZULÄSSIG: Ändern des öffentlichen Schlüssels einer Assembly**

### <a name="properties-fields-parameters-and-return-values"></a>Eigenschaften, Felder, Parameter und Rückgabewerte

- ✔️ **ZULÄSSIG: Ändern des Werts einer Eigenschaft, eines Felds, eines Rückgabewerts oder eines [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parameters in einen stärker abgeleiteten Typ**

  Beispielsweise kann eine Methode, die einen Typ von <xref:System.Object> zurückgibt, eine <xref:System.String>-Instanz zurückgeben. (Allerdings kann nicht die Signatur der Methode nicht geändert werden.)

- ✔️ **ZULÄSSIG: Erhöhen des Bereichs der zulässigen Werte für eine Eigenschaft oder einen Parameter, wenn der Member nicht [virtuell](../../csharp/language-reference/keywords/virtual.md) ist**

  Der Bereich der Werte, die an die Methode übergeben werden können oder vom Member zurückgegeben werden, kann erweitert werden, der Parameter- oder der Membertyp jedoch nicht. Beispielsweise können die an eine Methode übergebenen Werte von 0-124 auf 0-255 erweitert werden, der Parametertyp kann jedoch nicht von <xref:System.Byte> in <xref:System.Int32> geändert werden.

- ❌ **NICHT ZULÄSSIG: Erweitern des Bereichs der zulässigen Werte für eine Eigenschaft oder einen Parameter, wenn der Member [virtuell](../../csharp/language-reference/keywords/virtual.md) ist**

   Diese Änderung unterbricht bestehende, außer Kraft gesetzte Member, die für den erweiterten Wertebereich dann nicht korrekt funktionieren.

- ❌ **NICHT ZULÄSSIG: Verkleinern des Bereichs der zulässigen Werte für eine Eigenschaft oder einen Parameter**

- ❌ **NICHT ZULÄSSIG: Erweitern des Bereichs der zurückgegebenen Werte für eine Eigenschaft, ein Feld, einen Rückgabewert oder den [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parameter**

- ❌ **NICHT ZULÄSSIG: Ändern der zurückgegebenen Werte für eine Eigenschaft, ein Feld, einen Rückgabewert einer Methode oder den [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parameter**

- ❌ **NICHT ZULÄSSIG: Ändern des Standardwerts einer Eigenschaft, eines Felds oder eines Parameters**

- ❌ **NICHT ZULÄSSIG: Ändern der Genauigkeit eines numerischen Rückgabewerts**

- ❓ **ERFORDERT BEURTEILUNG: Eine Änderung im Analysieren von Eingaben und das Auslösen neuer Ausnahmen (auch wenn das Analyseverhalten nicht in der Dokumentation angegeben ist)**

### <a name="exceptions"></a>Ausnahmen

- ✔️ **ZULÄSSIG: Auslösen einer Ausnahme, die stärker abgeleitet ist als eine vorhandene**

  Da die neue Ausnahme eine Unterklasse einer vorhandenen Ausnahme ist, wird der bisherige Code zur Ausnahmebehandlung die Ausnahme weiterhin behandeln. In .NET Framework 4 wurden bei der Kulturerstellung und bei Abrufmethoden eine <xref:System.Globalization.CultureNotFoundException> anstelle einer <xref:System.ArgumentException> ausgelöst, wenn die Kultur nicht gefunden werden konnte. Da sich <xref:System.Globalization.CultureNotFoundException> aus <xref:System.ArgumentException> ableitet, ist dies eine zulässige Änderung.

- ✔️ **ZULÄSSIG: Auslösen einer spezifischeren Ausnahme als <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**

- ✔️ **ZULÄSSIG: Auslösen einer Ausnahme, die als nicht behebbar gilt**

  Nicht behebbare Ausnahmen sollten nicht abgefangen werden, sondern von einem übergeordneten Catch-All-Handler behandelt werden. Daher wird nicht erwartet, dass Benutzer über Code verfügen, der diese expliziten Ausnahmen abfängt. Nicht behebbare Ausnahmen sind:

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- ✔️ **ZULÄSSIG: Auslösen einer neuen Ausnahme in einem neuen Codepfad**

  Die Ausnahme darf nur für einen neuen Codepfad gelten, der mit neuen Parameterwerten oder einen neuen Zustand ausgeführt wird, und der nicht mit vorhandenem Code ausgeführt werden kann, der auf die vorherige Version abzielt.

- ✔️ **ZULÄSSIG: Entfernen eine Ausnahme, um ein stabileres Verhalten oder neue Szenarios zu ermöglichen**

  So kann beispielsweise eine `Divide`-Methode, die bisher nur positive Werte behandelt und andernfalls ein <xref:System.ArgumentOutOfRangeException> ausgelöst hat, so geändert werden, dass sowohl negative als auch positive Werte unterstützt werden, ohne eine Ausnahme auszulösen.

- ✔️ **ZULÄSSIG: Ändern des Texts einer Fehlermeldung**

  Entwickler sollten sich nicht auf den Text von Fehlermeldungen verlassen, die sich auch aufgrund der Kultur des Benutzers ändern.

- ❌ **NICHT ZULÄSSIG: Auslösen einer Ausnahme in allen Fällen, die oben nicht aufgeführt sind**

- ❌ **NICHT ZULÄSSIG: Entfernen einer Ausnahme in allen Fällen, die oben nicht aufgeführt sind**

### <a name="attributes"></a>Attribute

- ✔️ **ZULÄSSIG: Ändern des Werts eines Attributs, das *nicht* überwachbar ist**

- ❌ **NICHT ZULÄSSIG: Ändern des Werts eines Attributs, das *überwachbar* ist**

- ❓ **ERFORDERT BEURTEILUNG: Entfernen eines Attributs**

  In den meisten Fällen ist das Entfernen eines Attributs (wie <xref:System.NonSerializedAttribute>) ein Breaking Change.

## <a name="platform-support"></a>Plattformunterstützung

- ✔️ **ZULÄSSIG: Unterstützen eines Vorgangs auf einer Plattform, der bisher nicht unterstützt wurde**

- ❌ **NICHT ZULÄSSIG: Keine Unterstützung oder das Erfordern eines bestimmten Service Packs für einen Vorgang, der zuvor auf einer Plattform unterstützt wurde**

## <a name="internal-implementation-changes"></a>Änderungen an der internen Implementierung

- ❓ **ERFORDERT BEURTEILUNG: Ändern der Oberfläche eines internen Typs**

   Derartige Änderungen sind im Allgemeinen zulässig, auch wenn sie die private Reflektion unterbrechen. In einigen Fällen, in denen beliebte Bibliotheken von Drittanbietern oder eine große Anzahl von Entwicklern von den internen APIs abhängen, sind solche Änderungen möglicherweise nicht zulässig.

- ❓ **ERFORDERT BEURTEILUNG: Ändern der internen Implementierung eines Members**

  Diese Änderungen sind im Allgemeinen zulässig, auch wenn sie die private Reflektion unterbrechen. In einigen Fällen, in denen der Kundencode häufig von privater Reflexion abhängt, oder in denen die Änderung unbeabsichtigte Nebenwirkungen mit sich bringt, sind diese Änderungen möglicherweise nicht zulässig.

- ✔️ **ZULÄSSIG: Verbessern der Leistung eines Vorgangs**

   Die Möglichkeit, die Leistung eines Vorgangs zu ändern, ist unerlässlich, aber solche Änderungen können Code unterbrechen, der von der aktuellen Geschwindigkeit eines Vorgangs abhängt. Dies gilt insbesondere für Code, der vom Zeitpunkt des asynchronen Vorgangs abhängt. Die Leistungsänderung sollte keinen Einfluss auf das andere Verhalten der betreffenden API haben; andernfalls ist diese Änderung ein Breaking Change.

- ✔️ **ZULÄSSIG: Indirektes (und häufig negatives) Ändern der Leistung eines Vorgangs**

  Wenn die betreffende Änderung aus einem sonstigen Grund nicht als Breaking Change eingestuft wird, ist dies zulässig. Häufig müssen Maßnahmen ergriffen werden, die zusätzliche Vorgänge beinhalten können oder neue Funktionen hinzufügen. Dies hat fast immer Auswirkungen auf die Leistung, kann aber unerlässlich sein, damit die betreffende API wie erwartet funktioniert.

- ❌ **NICHT ZULÄSSIG: Ändern einer synchronen API in eine asynchrone API (und umgekehrt)**

## <a name="code-changes"></a>Codeänderungen

- ✔️ **ZULÄSSIG: Hinzufügen von [params](../../csharp/language-reference/keywords/params.md) zu einem Parameter**

- ❌ **NICHT ZULÄSSIG: Ändern einer [Struktur](../../csharp/language-reference/builtin-types/struct.md) in eine [Klasse](../../csharp/language-reference/keywords/class.md) und umgekehrt**

- ❌ **NICHT ZULÄSSIG: Hinzufügen des Schlüsselworts [checked](../../csharp/language-reference/keywords/virtual.md) zu einem Codeblock**

   Diese Änderung kann dazu führen, dass Code, der zuvor so ausgeführt wurde, eine <xref:System.OverflowException> ausgelöst. Dies ist nicht zulässig.

- ❌ **NICHT ZULÄSSIG: Entfernen von [params](../../csharp/language-reference/keywords/params.md) aus einem Parameter**

- ❌ **NICHT ZULÄSSIG: Ändern der Reihenfolge, in der Ereignisse ausgelöst werden**

  Entwickler können vernünftigerweise erwarten, dass Ereignisse in der gleichen Reihenfolge ausgelöst werden, und Entwicklercode hängt häufig von der Reihenfolge ab, in der Ereignisse ausgelöst werden.

- ❌ **NICHT ZULÄSSIG: Entfernen des Auftretens eines Ereignisses für eine bestimmte Aktion**

- ❌ **NICHT ZULÄSSIG: Ändern, wie oft bestimmte Ereignisse aufgerufen werden**

- ❌ **NICHT ZULÄSSIG: Hinzufügen von <xref:System.FlagsAttribute> zu einem Enumerationstyp**
