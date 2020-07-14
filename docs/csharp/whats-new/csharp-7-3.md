---
title: Neuerungen in C# 7.3
description: Eine Übersicht der neuen Features in C# 7.3
ms.date: 05/16/2018
ms.openlocfilehash: cd8f554516fb5078d9d2ed1eec787f36e8f4c7a7
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174756"
---
# <a name="whats-new-in-c-73"></a>Neuerungen in C# 7.3

Es gibt zwei Hauptdesigns in der C# 7.3-Version. Ein Design bietet Features, die ermöglichen, dass sicherer Code so leistungsfähig ist wie unsicherer Code. Das zweite Design bietet inkrementelle Verbesserungen vorhandener Funktionen. Darüber hinaus wurden in diesem Release neue Compileroptionen hinzugefügt.

Die folgenden neuen Features unterstützen das Design der besseren Leistung für sicheren Code:

- Sie können ohne Anheften auf feste Felder zugreifen.
- Sie können `ref` erneut lokale Variablen zuweisen.
- Sie können Initialisierer auf `stackalloc`-Arrays verwenden.
- Sie können `fixed`-Anweisungen mit jedem Typ verwenden, der ein Muster unterstützt.
- Sie können zusätzliche generische Einschränkungen verwenden.

Die folgenden Verbesserungen wurden an vorhandenen Features vorgenommen:

- Sie können `==` und `!=` mit Tupeltypen testen.
- Sie können Ausdrucksvariablen an mehreren Standorten verwenden.
- Sie können Attribute dem Unterstützungsfeld automatisch implementierter Eigenschaften anfügen.
- Die Auflösung der Methode, wenn Argumente um `in` differieren, wurde verbessert.
- Die Auflösung von Überladungen weist jetzt weniger mehrdeutige Fälle auf.

Die neuen Compileroptionen lauten:

- `-publicsign`, um das Signieren von Assemblys durch Open Source Software (OSS) zu ermöglichen.
- `-pathmap`, um eine Zuordnung für Quellverzeichnisse bereitzustellen.

Der übrige Teil dieses Artikels enthält Informationen und Links, über die Sie mehr zu den einzelnen Verbesserungen erfahren. Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:

1. Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.
1. Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.
1. Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp7* für das *try-samples*-Repository fest.
1. Führen Sie aus `dotnet try`.

## <a name="enabling-more-efficient-safe-code"></a>Ermöglichen von effizienterem sicherem Code

Sie sollten C#-Code sicher schreiben können, der so leistungsstark ist wie unsicherer Code. Sicherer Code vermeidet Fehlerklassen, z.B. Pufferüberläufe, verirrte Zeiger und andere Fehler beim Arbeitsspeicherzugriff. Diese neuen Features erweitern die Funktionen des überprüfbaren sicheren Codes. Schreiben Sie mithilfe sicherer Konstrukte mehr Code. Diese Features erleichtern dies.

### <a name="indexing-fixed-fields-does-not-require-pinning"></a>Indizieren von `fixed`-Feldern erfordert kein Anheften

Betrachten Sie diese Struktur:

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

In früheren Versionen von C# mussten Sie eine Variable für den Zugriff auf eine der ganzen Zahlen anheften, die Teil von `myFixedField` sind. Der folgende Code wird kompiliert, ohne die Variable `p` in einer separaten `fixed`-Anweisung anzuheften:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

Die Variable `p` greift auf ein Element in `myFixedField` zu. Sie müssen keine separate `int*`-Variable deklarieren. Beachten Sie, dass Sie immer noch einen `unsafe`-Kontext benötigen. In früheren Versionen von C# müssen Sie einen zweiten festen Zeiger deklarieren:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

Weitere Informationen finden Sie im Artikel zur [`fixed`-Anweisung](../language-reference/keywords/fixed-statement.md).

### <a name="ref-local-variables-may-be-reassigned"></a>Lokale `ref`-Variablen werden möglicherweise neu zugewiesen

Lokale `ref`-Variablen werden jetzt möglicherweise neu zugewiesen, um nach der Initialisierung auf verschiedene Instanzen zu verweisen. Der folgende Code wird jetzt kompiliert:

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

Weitere Informationen finden Sie im Artikel zu [`ref`-Rückgaben und lokalen `ref`-Variablen](../programming-guide/classes-and-structs/ref-returns.md) und im Artikel zu [`foreach`](../language-reference/keywords/foreach-in.md).

### <a name="stackalloc-arrays-support-initializers"></a>`stackalloc`-Arrays unterstützen Initialisierer

Sie konnten schon die Werte für Elemente in einem Array angeben, wenn Sie es initialisierten:

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

Nun kann die gleiche Syntax auf Arrays angewendet werden, die mit `stackalloc` deklariert werden:

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

Weitere Informationen finden Sie im Artikel zum [`stackalloc`-Operator](../language-reference/operators/stackalloc.md).

### <a name="more-types-support-the-fixed-statement"></a>Weitere Typen unterstützen die `fixed`-Anweisung

Die `fixed`-Anweisung unterstützte eine begrenzte Anzahl von Typen. Ab C# 7.3 kann jeder Typ, der eine `GetPinnableReference()`-Methode enthält, die eine `ref T` oder `ref readonly T` zurückgibt, `fixed` sein. Dieses Feature hinzuzufügen, bedeutet, dass `fixed` mit <xref:System.Span%601?displayProperty=nameWithType> und verwandten Typen genutzt werden kann.

Weitere Informationen finden Sie im Artikel zur [`fixed`-Anweisung](../language-reference/keywords/fixed-statement.md) in der Sprachreferenz.

### <a name="enhanced-generic-constraints"></a>Verbesserte generische Einschränkungen

Sie können jetzt Typ <xref:System.Enum?displayProperty=nameWithType> oder <xref:System.Delegate?displayProperty=nameWithType> als Basisklasseneinschränkungen für einen Typparameter angeben.

Sie können auch die neue `unmanaged`-Einschränkung nutzen, um anzugeben, dass der Typparameter ein [nicht verwalteter Non-Nullable-Typ](../language-reference/builtin-types/unmanaged-types.md) sein muss.

Weitere Informationen finden Sie in den Artikeln zu generischen [`where`-Einschränkungen](../language-reference/keywords/where-generic-type-constraint.md) und [Einschränkungen für Typparameter](../programming-guide/generics/constraints-on-type-parameters.md).

Das Hinzufügen dieser Einschränkungen zu vorhandenen Typen ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes). Geschlossene generische Typen erfüllen diese neuen Einschränkungen möglicherweise nicht mehr.

## <a name="make-existing-features-better"></a>Vorhandene Features besser machen

Das zweite Design enthält Verbesserungen der Features in der Sprache. Die Produktivität dieser Features wird verbessert, wenn sie in C# geschrieben werden.

### <a name="tuples-support--and-"></a>Tupel unterstützen `==` und `!=`

Die C#-Tupeltypen unterstützen jetzt `==` und `!=`. Weitere Informationen finden Sie im Abschnitt [Tupelgleichheit](../language-reference/builtin-types/value-tuples.md#tuple-equality) im Artikel [Tupeltypen](../language-reference/builtin-types/value-tuples.md).

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a>Anfügen von Attributen zu den Unterstützungsfeldern für automatisch implementierte Eigenschaften

Diese Syntax wird jetzt unterstützt:

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

Das Attribut `SomeThingAboutFieldAttribute` wird auf das vom Compiler generierte Unterstützungsfeld für `SomeProperty` angewendet. Weitere Informationen finden Sie unter [attributes](../programming-guide/concepts/attributes/index.md) im C#-Programmierhandbuch.

### <a name="in-method-overload-resolution-tiebreaker"></a>Tiebreaker zur Auflösung der Überladung der `in`-Methode

Wenn der `in`-Argumentmodifizierer hinzugefügt wurde, verursachten diese beiden Methoden eine Mehrdeutigkeit:

```csharp
static void M(S arg);
static void M(in S arg);
```

Jetzt ist die Überladung des Werts „by“ (im vorherigen Beispiel an erster Stelle) besser als die „by readonly“-Verweisversion. Um die Version mit dem readonly-Verweisargument aufzurufen, müssen Sie auch den `in`-Modifizierer beim Aufrufen der Methode einbeziehen.

> [!NOTE]
> Dies wurde als Fehlerkorrektur implementiert. Dies ist selbst mit der Sprachversion „7.2“ nicht mehr mehrdeutig.

Weitere Informationen finden Sie im Artikel zum [`in`-Parametermodifizierer](../language-reference/keywords/in-parameter-modifier.md).

### <a name="extend-expression-variables-in-initializers"></a>Erweitern der Ausdrucksvariablen in Initialisierern

Die in C# 7.0 zum Zulassen von `out`-Variablendeklarationen hinzugefügte Syntax wurde erweitert, sodass sie Feldinitialisierer, Eigenschafteninitialisierer, Konstruktorinitialisierer und Abfrageklauseln umfasst. Sie ermöglicht Code wie im folgenden Beispiel:

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a>Verbesserte Überladungskandidaten

In jedem Release werden die Überladungsauflösungsregeln für Situationen aktualisiert, in denen mehrdeutige Methodenaufrufe eine „naheliegende“ Auswahlmöglichkeit haben. In diesem Release werden drei neue Regeln hinzufügt, damit der Compiler die naheliegende Auswahlmöglichkeit nutzt:

1. Wenn eine Methodengruppe sowohl Instanz- als auch statische Member enthält, verwirft der Compiler die Instanzmember, wenn die Methode ohne Instanzempfänger oder -kontext aufgerufen wurde. Der Compiler verwirft die statischen Member, wenn die Methode mit einem Instanzempfänger aufgerufen wurde. Wenn kein Empfänger vorhanden ist, bezieht der Compiler nur statische Member in einen statischen Kontext ein – andernfalls sowohl statische als auch Instanzmember. Wenn unklar ist, ob der Empfänger eine Instanz oder ein Typ ist, bezieht der Compiler beides ein. Ein statischer Kontext, wo ein impliziter `this`-Instanzempfänger nicht verwendet werden kann, enthält den Text von Membern, wo kein `this` definiert ist, z.B. statische Member, sowie Orte, an denen `this` nicht verwendet werden kann, z.B. Feld- und Konstruktorinitialisierer.
1. Wenn eine Methodengruppe einige generische Methoden enthält, deren Typargumente ihre Einschränkungen nicht erfüllen, werden diese Member aus dem Satz von Kandidaten entfernt.
1. Für eine Methodengruppenkonvertierung werden Kandidatenmethoden, deren Rückgabetyp nicht mit dem des Delegaten übereinstimmt, aus dem Satz entfernt.

Sie werden diese Änderung bemerken, da Sie weniger Compilerfehler für mehrdeutige Methodenüberladungen finden werden, wenn Sie sicher sind, welche Methode besser ist.

## <a name="new-compiler-options"></a>Neue Compileroptionen

Neue Compileroptionen unterstützen neue Build- und DevOpsszenarien für C#-Programme.

### <a name="public-or-open-source-signing"></a>Öffentliche oder Open Source-Signierung

Die `-publicsign`-Compileroption weist den Compiler an, die Assembly mit einem öffentlichen Schlüssel zu signieren. Die Assembly wird als signiert markiert, aber die Signatur wird dem öffentlichen Schlüssel entnommen. Mit dieser Option können Sie signierte Assemblys aus Open Source-Projekten mit einem öffentlichen Schlüssel erstellen.

Weitere Informationen finden Sie im Artikel zur [Compileroption „-publicsign“](../language-reference/compiler-options/publicsign-compiler-option.md).

### <a name="pathmap"></a>pathmap

Die `-pathmap`-Compileroption weist den Compiler an, Quellpfade aus der Buildumgebung mit zugeordneten Quellpfaden zu ersetzen. Die `-pathmap`-Option bestimmt den Quellpfad, der vom Compiler in PDB-Dateien oder für <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> geschrieben wird.

Weitere Informationen finden Sie im Artikel zur [Compileroption „-pathmap“](../language-reference/compiler-options/pathmap-compiler-option.md).
