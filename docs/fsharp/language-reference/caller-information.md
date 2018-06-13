---
title: Aufruferinformationen (f#)
description: Beschreibt, wie, Aufrufer-Informationsattribute Argument Aufruferinformationen von einer Methode abzurufen.
ms.date: 04/25/2017
ms.openlocfilehash: 6fd80213cdaf2c4662fd4c2ed9eaf8949e397efe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564781"
---
# <a name="caller-information"></a>Aufruferinformationen

Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen. Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen. Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.

Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt. Die folgende Tabelle enthält die Aufrufer-Informationsattribute angegeben, die in definiert werden die [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) Namespace:

|Attribut|Beschreibung|Typ|
|---------|-----------|----|
|[CallerFilePath](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|Vollständiger Pfad der Quelldatei, die den Aufrufer enthält. Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.|`String`
|[CallerLineNumber](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.|`Integer`|
|[CallerMemberName](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|Der Methoden- oder Eigenschaftenname des Aufrufers. Finden Sie im Abschnitt "Elementnamen" weiter unten in diesem Thema.|`String`|

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie diese Attribute verwenden können, um einen Aufrufer zu verfolgen.

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a>Hinweise

Aufrufer-Informationsattribute können nur auf optionale Parameter angewendet werden. Sie müssen einen expliziten Wert für jeden optionalen Parameter angeben. Der Aufrufer-Informationsattribute dazu führen, dass den Compiler den korrekten Wert für jeden optionalen Parameter mit einem Aufrufer-Informationsattribute-Attribut ergänzt schreiben.

Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben. Im Gegensatz zu den Ergebnissen von der [StackTrace](/dotnet/api/system.diagnostics.stacktrace) -Eigenschaft für Ausnahmen werden die Ergebnisse nicht durch verbergen beeinflusst.

Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.

## <a name="member-names"></a>Elementnamen

Sie können die [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) Attribut, um den Membernamen nicht als angeben zu müssen eine `String` Argument an die aufgerufene Methode. Mit dieser Technik, umgehen Sie das Problem, die Umgestaltung mit Umbenennung ändern nicht den `String` Werte. Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:

* Verwenden der Ablaufverfolgung und der Diagnoseprogramme
* Implementieren der [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) -Schnittstelle beim Binden von Daten. Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann. Ohne die [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) -Attribut, müssen Sie den Eigenschaftennamen als Literal angeben.

Im folgende Diagramm sind die Membernamen aufgeführt, die zurückgegeben werden, wenn Sie das CallerMemberName-Attribut verwenden.

|Aufrufe erfolgen in|Ergebnis des Membernamens|
|-------------------|------------------|
|Methode, Eigenschaft oder Ereignis|Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.|
|Konstruktor|Die Zeichenfolge ".ctor"|
|Statischer Konstruktor|Die Zeichenfolge ".cctor"|
|Destruktor|Die Zeichenfolge "Finalize"|
|Benutzerdefinierte Operatoren oder Konvertierungen|Der generierte Name für den Member, beispielsweise "op_Addition".|
|Attributkonstruktor|Der Name des Members, auf den das Attribut angewendet wird. Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.|
|Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)|Der Standardwert des optionalen Parameters.|

## <a name="see-also"></a>Siehe auch
 [Attribute](attributes.md)  
 [Benannte Argumente](parameters-and-arguments.md#named-arguments)  
 [Optionale Parameter](parameters-and-arguments.md#optional-parameters)  
