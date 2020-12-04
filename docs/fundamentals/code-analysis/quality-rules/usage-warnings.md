---
title: Verwendungs Regeln (Code Analyse)
description: Erfahren Sie mehr über die Verwendungs Regeln für die Code Analyse.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.usagerules
helpviewer_keywords:
- rules, usage
- managed code analysis rules, usage rules
- usage rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: c8b14d2f92502d5a82e41a322e599745bdcf8b85
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "96591909"
---
# <a name="usage-rules"></a>Nutzungsregeln

Verwendungs Regeln unterstützen die ordnungsgemäße Verwendung von .net.

## <a name="in-this-section"></a>In diesem Abschnitt

|Regel|Beschreibung|
|----------|-----------------|
|[CA1801: Nicht verwendete Parameter überprüfen.](ca1801.md)|Eine Methodensignatur enthält einen Parameter, der nicht im Methodentext verwendet wird.|
|[CA1816: GC.SuppressFinalize korrekt aufrufen.](ca1816.md)|Eine Methode, bei der es sich um eine-Implementierung handelt, wird nicht aufgerufen `GC.SuppressFinalize` , oder eine Methode, die keine Implementierung von `Dispose` -aufrufen ist `GC.SuppressFinalize` . oder eine-Methode ruft `GC.SuppressFinalize` auf und übergibt etwas anderes als `this` ( `Me` in Visual Basic).|
|[CA2200: Erneut ausführen, um Stapeldetails beizubehalten.](ca2200.md)|Eine Ausnahme wird erneut ausgelöst, und die Ausnahme wird in der throw-Anweisung explizit angegeben. Wenn eine Ausnahme durch Angeben der Ausnahme in der throw-Anweisung erneut ausgelöst wird, geht die Liste der Methoden, die zwischen der Methode, durch die die Ausnahme ursprünglich ausgelöst wurde, und der aktuellen Methode aufgerufen wurden, verloren.|
|[CA2201: Keine reservierten Ausnahmetypen auslösen.](ca2201.md)|Dadurch wird der ursprüngliche Fehler schwer zu erkennen und zu debuggen.|
|[CA2207: Statische Felder für Werttyp inline initialisieren.](ca2207.md)|Ein Werttyp deklariert einen expliziten statischen Konstruktor. Um einen Verstoß gegen diese Regel zu beheben, initialisieren Sie alle statischen Daten nach deren Deklaration und entfernen den statischen Konstruktor.|
|[CA2208: Argumentausnahmen korrekt instanziieren.](ca2208.md)|Der (parameterlose) Standardkonstruktor eines Ausnahmetyps wird aufgerufen, der ArgumentException ist oder davon abgeleitet wird, oder ein falsches Zeichenfolgenargument wird an einen parametrisierten Konstruktor eines Ausnahmetyps übergeben, der ArgumentException ist oder davon abgeleitet wird.|
|[CA2211: Nicht konstante Felder sollten nicht sichtbar sein.](ca2211.md)|Statische Felder, die keine Konstanten sind oder schreibgeschützt sind, sind nicht Thread sicher. Der Zugriff auf ein solches Feld muss sorgfältig gesteuert werden und erfordert erweiterte Programmierverfahren für die Synchronisierung des Zugriffs auf das Klassenobjekt.|
|[CA2213: Verwerfbare Felder verwerfen.](ca2213.md)|Ein Typ, der implementiert, <xref:System.IDisposable?displayProperty=fullName> deklariert Felder mit Typen, die ebenfalls implementieren `IDisposable` . Die- `Dispose` Methode des-Felds wird nicht von der- `Dispose` Methode des deklarierenden Typs aufgerufen.|
|[CA2214: Überschreibbare Methoden in Konstruktoren nicht aufrufen.](ca2214.md)|Wenn ein Konstruktor eine virtuelle Methode aufruft, ist es möglich, dass der Konstruktor für die-Instanz, die die-Methode aufruft, nicht ausgeführt wurde.|
|[CA2215: Dispose-Methoden müssen die Dispose-Funktion der Basisklasse aufrufen.](ca2215.md)|Wenn ein Typ von einem verwerfbaren Typ erbt, muss er die- `Dispose` Methode des Basistyps aus seiner eigenen- `Dispose` Methode abrufen.|
|[CA2216: Verwerfbare Typen sollten einen Finalizer deklarieren.](ca2216.md)|Ein Typ, <xref:System.IDisposable?displayProperty=fullName> der implementiert und über Felder verfügt, die die Verwendung nicht verwalteter Ressourcen vorschlagen, implementiert keinen Finalizer, wie in beschrieben `Object.Finalize` .|
|[CA2217: Enumerationen nicht mit FlagsAttribute markieren.](ca2217.md)|Eine extern sichtbare Enumeration ist mit markiert `FlagsAttribute` , und Sie verfügt über einen oder mehrere Werte, die nicht aus zwei oder einer Kombination der anderen definierten Werte für die Enumeration bestehen.|
|[CA2218: GetHashCode beim Überschreiben von Equals überschreiben.](ca2218.md)|Ein öffentlicher Typ überschreibt, <xref:System.Object.Equals%2A?displayProperty=fullName> aber nicht außer Kraft <xref:System.Object.GetHashCode%2A?displayProperty=fullName> .|
|[CA2219: Keine Ausnahmen in Ausnahmeklauseln auslösen.](ca2219.md)|Wenn eine Ausnahme in einer finally-Klausel oder fault-Klausel ausgelöst wird, wird die aktive Ausnahme von der neuen Ausnahme verdeckt. Wenn eine Ausnahme in einer filter-Klausel ausgelöst wird, fängt die Laufzeit die Ausnahme automatisch ab. Dadurch wird der ursprüngliche Fehler schwer zu erkennen und zu debuggen.|
|[CA2224: Equals beim Überladen von Gleichheitsoperatoren überschreiben.](ca2224.md)|Ein öffentlicher Typ implementiert den Gleichheits Operator, überschreibt jedoch nicht <xref:System.Object.Equals%2A?displayProperty=fullName> .|
|[CA2225: Operatorüberladungen weisen benannte Alternativen auf.](ca2225.md)|Es wurde eine Operatorüberladung erkannt, und die erwartete benannte Alternativmethode wurde nicht gefunden. Der benannte Alternative Member bietet Zugriff auf die gleiche Funktionalität wie der-Operator und wird für Entwickler bereitgestellt, die in Sprachen programmieren, die überladene Operatoren nicht unterstützen.|
|[CA2226: Operatoren sollten symmetrische Überladungen aufweisen.](ca2226.md)|Ein Typ implementiert den Gleichheits-oder Ungleichheits Operator und implementiert nicht den umgekehrten Operator.|
|[CA2227: Sammlungseigenschaften sollten schreibgeschützt sein.](ca2227.md)|Eine schreibbare Auflistungseigenschaft ermöglicht es Benutzern, die Auflistung durch eine andere Auflistung zu ersetzen. Eine schreibgeschützte Eigenschaft sorgt dafür, dass die Auflistung nicht mehr ersetzt wird, lässt aber dennoch das Festlegen einzelner Member zu.|
|[CA2229: Serialisierungskonstruktoren implementieren.](ca2229.md)|Um einen Verstoß gegen diese Regel zu beheben, implementieren Sie den Serialisierungskonstruktor. Definieren Sie den Konstruktor bei einer versiegelten Klasse als privaten Konstruktor. Definieren Sie ihn andernfalls als geschützten Konstruktor.|
|[CA2231: Überladen Sie den Gleichheitsoperator beim Überschreiben von ValueType.Equals.](ca2231.md)|Ein Werttyp überschreibt, `Object.Equals` aber implementiert den Gleichheits Operator nicht.|
|[CA2234: Übergeben Sie System.Uri-Objekte anstelle von Zeichenfolgen.](ca2234.md)|Eine Methode wird aufgerufen, die über einen Zeichenfolgenparameter verfügt, dessen Name "uri", "URI", "urn", "URN", "url" oder "URL" enthält.  Der deklarierende Typ der Methode enthält eine entsprechende Methoden Überladung, die über einen- <xref:System.Uri?displayProperty=fullName> Parameter verfügt.|
|[CA2235: Alle nicht serialisierbaren Felder markieren.](ca2235.md)|Ein Instanzenfeld eines Typs, der nicht serialisierbar ist, ist in einem serialisierbaren Typ deklariert.|
|[CA2237: ISerializable-Typen mit SerializableAttribute markieren.](ca2237.md)|Um vom Common Language Runtime als serialisierbar erkannt zu werden, müssen Typen mit dem SerializableAttribute-Attribut markiert werden, auch wenn der Typ durch die Implementierung der-Schnittstelle eine benutzerdefinierte Serialisierungsroutine verwendet `ISerializable` .|
|[CA2241: Geben Sie die korrekte Anzahl für Formatierungsmethoden an.](ca2241.md)|Das an über gegebene Format-Argument <xref:System.String.Format%2A?displayProperty=nameWithType> enthält kein Format Element, das jedem Objekt Argument entspricht, oder umgekehrt.|
|[CA2242: Ordnungsgemäß auf NaN testen.](ca2242.md)|Dieser Ausdruck testet einen Wert mit `Single.Nan` oder `Double.Nan` . Verwenden `Single.IsNan(Single)` `Double.IsNan(Double)` Sie oder, um den Wert zu testen.|
|[CA2243: Attribute-Zeichenfolgenliterale müssen stets richtig analysiert werden.](ca2243.md)|Der zeichenfolgenliteralparameter eines Attributs wird für eine URL, eine GUID oder eine Version nicht ordnungsgemäß analysiert.|
|[CA2244: Keine Initialisierungen indizierter Elemente duplizieren](ca2244.md)|Ein Objektinitialisierer verfügt über mehr als einen indizierten Elementinitialisierer mit demselben Konstanten Index. Alle außer der letzte Initialisierer sind redundant.|
|[CA2245: Keine Zuweisung einer Eigenschaft zu sich selbst](ca2245.md)|Eine Eigenschaft wurde versehentlich selbst zugewiesen.|
|[CA2246: Keine Zuweisung eines Symbols und seines Members in der gleichen Anweisung](ca2246.md)|Es wird nicht empfohlen, ein Symbol und dessen Member, d. h. ein Feld oder eine Eigenschaft, in derselben Anweisung zuzuweisen. Es ist nicht klar, ob der Element Zugriff dazu gedacht war, den alten Wert des Symbols vor der Zuweisung oder den neuen Wert aus der Zuweisung in dieser Anweisung zu verwenden.|
|[CA2247: Anstelle einer TaskContinuationOptions-Enumeration muss eine TaskCreationOptions-Enumeration als Argument an den TaskCompletionSource-Konstruktor übergeben werden.](ca2246.md)|TaskCompletionSource verfügt über Konstruktoren, die taskkreationoptions verwenden, die die zugrunde liegende Aufgabe steuern, und Konstruktoren, die den Objektzustand annehmen, der in der Aufgabe gespeichert ist.  Das versehentliche übergeben von TaskContinuationOptions anstelle von taskkreationoptions führt dazu, dass der Aufruf die Optionen als Zustand behandelt.|
|[CA2248: Geben Sie ein korrektes "Aufzählungs Argument" für "" "" "" ".](ca2248.md)|Der als Argument an den `HasFlag` Methodenaufruf umgegebene Aufzählungs Typ unterscheidet sich vom aufrufenden Aufzählungs Typen.|
|[CA2249: Erwägen Sie die Verwendung von "String.Contains" anstelle von "String.IndexOf"](ca2249.md)|Aufrufe `string.IndexOf` von, bei denen das Ergebnis verwendet wird, um zu überprüfen, ob eine Teil Zeichenfolge vorhanden oder nicht vorhanden ist, können durch ersetzt werden `string.Contains` .|
