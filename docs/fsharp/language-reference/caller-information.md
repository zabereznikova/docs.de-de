---
title: Aufruferinformationen
description: Beschreibt, wie aufruferinfo-Argument Attribute verwendet werden, um Aufruferinformationen von einer Methode abzurufen.
ms.date: 11/04/2019
ms.openlocfilehash: 700cde26fbe4e6c48155f88bfc63af59af86cfe2
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739775"
---
# <a name="caller-information"></a>Aufruferinformationen

Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen. Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen. Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.

Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt. In der folgenden Tabelle sind die Aufrufer-Informations Attribute aufgelistet, die im [System. Runtime. CompilerServices](/dotnet/api/system.runtime.compilerservices) -Namespace definiert sind:

|attribute|BESCHREIBUNG|type|
|---------|-----------|----|
|[Callerfilepath](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|Vollständiger Pfad der Quelldatei, die den Aufrufer enthält. Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.|`String`
|[Callerlinenumber](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.|`Integer`|
|[CallerMemberName](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|Der Methoden- oder Eigenschaftenname des Aufrufers. Weitere Informationen finden Sie im Abschnitt Elementnamen weiter unten in diesem Thema.|`String`|

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie diese Attribute zum Verfolgen eines Aufrufers verwenden können.

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member _.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf $"Message: {message}")
        Trace.WriteLine(sprintf $"Member name: {memberName}")
        Trace.WriteLine(sprintf $"Source file path: {path}")
        Trace.WriteLine(sprintf $"Source line number: {line}")
```

## <a name="remarks"></a>Bemerkungen

Aufrufer-Informations Attribute können nur auf optionale Parameter angewendet werden. Die Attribute für Aufruferinformationen bewirken, dass der Compiler den richtigen Wert für jeden optionalen Parameter schreibt, der mit einem aufruferinformationsattribut versehen ist

Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben. Im Gegensatz zu den Ergebnissen der [StackTrace](/dotnet/api/system.diagnostics.stacktrace) -Eigenschaft für Ausnahmen sind die Ergebnisse nicht von der Verschleierung betroffen.

Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.

## <a name="member-names"></a>Membernamen

Sie können das- [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) Attribut verwenden, um zu vermeiden, dass der Elementname als `String` Argument für die aufgerufene Methode angegeben wird. Auf diese Weise umgehen Sie das Problem, dass durch die Umgestaltung mit Umbenennung die `String`-Werte nicht geändert werden. Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:

- Verwenden der Ablaufverfolgung und der Diagnoseprogramme
- Implementieren der [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) -Schnittstelle beim Binden von Daten. Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann. Ohne das- [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) Attribut müssen Sie den Eigenschaftsnamen als Literalwert angeben.

Das folgende Diagramm zeigt die Elementnamen, die zurückgegeben werden, wenn Sie das callermembership Name-Attribut verwenden.

|Aufrufe erfolgen in|Membernamenergebnis|
|-------------------|------------------|
|Methode, Eigenschaft oder Ereignis|Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.|
|Konstruktor|Die Zeichenfolge „.ctor“|
|Statischer Konstruktor|Die Zeichenfolge „.cctor“|
|Destruktor|Die Zeichenfolge „Finalize“|
|Benutzerdefinierte Operatoren oder Konvertierungen|Der generierte Name für den Member, beispielsweise „op_Addition“.|
|Attributkonstruktor|Der Name des Members, auf den das Attribut angewendet wird. Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.|
|Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)|Der Standardwert des optionalen Parameters.|

## <a name="see-also"></a>Siehe auch

- [Attribute](attributes.md)
- [Benannte Argumente](parameters-and-arguments.md#named-arguments)
- [Optionale Parameter](parameters-and-arguments.md#optional-parameters)
