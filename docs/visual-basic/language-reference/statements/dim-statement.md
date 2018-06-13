---
title: Dim-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: b3384b771748a1f2c9e841407042f81ce6ebe76d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234726"
---
# <a name="dim-statement-visual-basic"></a>Dim-Anweisung (Visual Basic)
Deklariert und reserviert Speicherplatz für eine oder mehrere Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a>Teile  
  
-   `attributelist`  
  
     Dies ist optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `accessmodifier`  
  
     Dies ist optional. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [Protected Friend](../../language-reference/modifiers/protected-friend.md)
    
    - [Geschützt privat](../../language-reference/modifiers/private-protected.md)

     Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `Shared`  
  
     Dies ist optional. Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Dies ist optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Static`  
  
     Dies ist optional. Finden Sie unter [statische](../../../visual-basic/language-reference/modifiers/static.md).  
  
-   `ReadOnly`  
  
     Dies ist optional. Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WithEvents`  
  
     Dies ist optional. Gibt an, dass diese Objektvariablen, die auf Instanzen einer Klasse verweisen, die Ereignisse auslösen kann. Finden Sie unter [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).  
  
-   `variablelist`  
  
     Erforderlich. Liste der Variablen, die in dieser Anweisung deklariert wird.  
  
     `variable [ , variable ... ]`  
  
     Jede `variable` weist folgende Syntax und Bestandteile auf:  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`variablename`|Erforderlich. Der Name der Variablen. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
    |`boundslist`|Dies ist optional. Liste der Grenzen jeder Dimension des Arrayvariable.|  
    |`New`|Dies ist optional. Erstellt eine neue Instanz der Klasse bei der `Dim` Anweisung wird ausgeführt.|  
    |`datatype`|Dies ist optional. Der Datentyp der Variablen.|  
    |`With`|Dies ist optional. Führt der Objektinitialisiererliste.|  
    |`propertyname`|Dies ist optional. Der Name einer Eigenschaft in der Klasse werden Sie eine Instanz von herstellen.|  
    |`propinitializer`|Nach der erforderlichen `propertyname` =. Der Ausdruck, der ausgewertet und den Namen der Eigenschaft zugewiesen wird.|  
    |`initializer`|Optional, wenn `New` nicht angegeben wird. Ausdruck, der ausgewertet und bei der Erstellung der Variablen zugewiesen ist.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Basic-Compiler verwendet den `Dim` Anweisung, um festzustellen, Datentyp der Variablen und andere Informationen, z. B. welcher Code auf die Variable zugreifen kann. Das folgende Beispiel deklariert eine Variable für ein `Integer` Wert.  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 Für einen Verweistyp handelt, verwenden Sie die `New` -Schlüsselwort zum Erstellen einer neuen Instanz der Klasse oder Struktur, durch den-Datentyp angegeben ist. Bei Verwendung von `New`, einen Initialisiererausdruck nicht verwendet. Stattdessen geben Sie Argumente, sofern diese erforderlich ist, an den Konstruktor der Klasse sind aus denen Sie die Variable erstellen.  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 Sie können eine Variable in einer Prozedur, Block, Klasse, Struktur oder Modul deklarieren. Sie können eine Variable in einer Quelldatei, Namespace oder Schnittstelle nicht deklarieren. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Ist eine Variable, die auf Modulebene außerhalb einer Prozedur deklariert ist ein *Membervariable* oder *Feld*. Membervariablen sind im Gültigkeitsbereich ihrer Klasse, Struktur oder eines Moduls. Eine auf Prozedurebene deklarierte Variable ist eine *lokale Variable*. Lokale Variablen sind nur innerhalb ihrer Prozedur oder eines Blocks.  
  
 Die folgenden Zugriffsmodifizierer werden zum Deklarieren von Variablen, die außerhalb einer Prozedur verwendet: `Public`, `Protected`, `Friend`, `Protected Friend`, und `Private`. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Die `Dim` Schlüsselwort ist optional und in der Regel nicht angegeben wird, wenn Sie eine der folgenden Modifizierer angeben: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, oder `WithEvents`.  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 Wenn `Option Explicit` ist (Standard), erfordert der Compiler eine Deklaration für jede Variable, die Sie verwenden. Weitere Informationen finden Sie unter [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md).  
  
## <a name="specifying-an-initial-value"></a>Einen Anfangswert angeben  
 Sie können einer Variablen einen Wert zuweisen, während der Erstellung. Für einen Werttyp aufweist, verwenden Sie eine *Initialisierer* , geben Sie einen Ausdruck, der Variablen zugewiesen werden soll. Der Ausdruck muss auf eine Konstante ausgewertet werden, die zur Kompilierzeit berechnet werden kann.  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 Wenn ein Initialisierer angegeben ist und ein Datentyp nicht, in angegeben ist einer `As` -Klausel, *Typrückschluss* wird verwendet, um den Datentyp aus dem Initialisierer abzuleiten. Im folgenden Beispiel sowohl `num1` und `num2` sind stark typisiert als ganze Zahlen. In der zweiten Deklaration leitet der Typrückschluss den Typ aus dem Wert 3 ab.  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 Typrückschluss ist auf Prozedurebene gültig. Es gilt nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle. Weitere Informationen zu den Typ abzuleiten, finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [lokalen Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Informationen, was geschieht, wenn ein Datentyp oder einen Initialisierer nicht angegeben ist, finden Sie unter [-Standarddatentypen und-Werte](../../../visual-basic/language-reference/statements/dim-statement.md#default) weiter unten in diesem Thema.  
  
 Können Sie eine *-Objekt Initialisierer* Instanzen benannte und anonyme Typen zu deklarieren. Der folgende Code erstellt eine Instanz von einem `Student` Klasse und verwendet einen Objektinitialisierer, um Eigenschaften zu initialisieren.  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 Weitere Informationen über Objektinitialisierer finden Sie unter [wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Objektinitialisierer: benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), und [anonyme Typen ](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="declaring-multiple-variables"></a>Mehrere Variablen deklariert werden  
 Sie können mehrere Variablen in einer Deklaration-Anweisung deklarieren, die den Variablennamen für jede einzelne und nach jeder Arrayname mit Klammern angeben. Mehrere Variablen werden durch Kommas voneinander getrennt.  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 Wenn Sie mehr als eine Variable mit einem deklarieren `As` -Klausel keine Initialisierer für diese Gruppe von Variablen bereitstellen.  
  
 Sie können für verschiedene Variablen unterschiedliche Datentypen angeben, indem Sie eine separate `As` -Klausel für jede Variable, die Sie deklarieren. Jede Variable nimmt in der ersten angegebenen Datentyp `As` -Klausel nach seiner `variablename` Teil.  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>Arrays  
 Sie können deklarieren eine Variable für ein *Array*, die mehrere Werte enthalten kann. Um anzugeben, dass eine Variable ein Array enthält, führen Sie die `variablename` sofort mit Klammern. Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Sie können die untere und obere Grenze der einzelnen Dimensionen eines Arrays angeben. Um dies zu erreichen, fügen einen `boundslist` innerhalb der Klammern. Für jede Dimension die `boundslist` gibt die obere Grenze und optional die untere Grenze. Die untere Grenze ist immer 0 (null), ob Sie es angeben. Jeder Index kann von 0 (null), über den Wert der oberen Grenze variieren.  
  
 Die folgenden beiden Anweisungen sind gleichwertig. Jede Anweisung deklariert ein Array von 21 `Integer` Elemente. Wenn Sie das Array zugreifen, kann der Index von 0 bis 20 abweichen.  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 Die folgende Anweisung deklariert ein zweidimensionales Array vom Typ `Double`. Das Array verfügt über 6 Spalten (5 + 1) jeweils 4 Zeilen (3 + 1). Beachten Sie, dass eine obere Grenze den höchsten möglichen Wert für den Index, nicht die Länge der Dimension darstellt. Die Länge der Dimension ist die obere Grenze plus eins.  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 Ein Array kann von 1 bis 32 Dimensionen aufweisen.  
  
 Sie können alle Grenzen in der Arraydeklaration eines leer lassen. Wenn Sie so vorgehen, das Array verfügt über die Anzahl der Dimensionen, die Sie angeben, aber es ist nicht initialisiert. Der Wert des `Nothing` bis Sie mindestens initialisieren einige seiner Elemente. Die `Dim` -Anweisung darf Grenzen für alle Dimensionen oder für keine Dimensionen angegeben.  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 Wenn das Array mehr als eine Dimension hat, müssen Sie zwischen den Klammern an, dass die Anzahl der Dimensionen als Trennzeichen einschließen.  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 Sie können deklarieren eine *Array der Länge null* durch deklarieren eine der Dimensionen des Arrays als-1 sein. Eine Variable, ein Array der Länge 0 (null) enthält, verfügt nicht über den Wert `Nothing`. Arrays mit der Länge 0 (null) sind bestimmte Funktionen der common Language Runtime erforderlich. Wenn Sie versuchen, ein solches Array zuzugreifen, tritt eine Laufzeitausnahme. Weitere Informationen finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Sie können die Werte eines Arrays mit einem Arrayliteral initialisieren. Umschließen Sie zu diesem Zweck die Initialisierungswerte mit geschweiften Klammern (`{}`).  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 Für mehrdimensionale Arrays wird die Initialisierung für jede separate Dimension in der geschweiften Klammern in der äußeren Dimension eingeschlossen. Die Elemente werden in zeilengerichteter Reihenfolge angegeben.  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 Weitere Informationen zu Arrayliterale, finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
##  <a name="default"></a> Standarddatentypen und-Werte  
 Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.  
  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|---|---|---|---|  
|Nein|Nein|`Dim qty`|Wenn [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) ist off (Standardeinstellung), wird die Variable festgelegt, um `Nothing`.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Nein|Ja|`Dim qty = 5`|Wenn [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) ist (Standard), übernimmt die Variable die Daten des Initialisierers geben. Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Finden Sie in der Tabelle weiter unten in diesem Abschnitt.|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|  
  
 Wenn Sie einen Datentyp angeben, aber Sie keine Initialisierer geben, initialisiert Visual Basic die Variable auf den Standardwert für seinen Datentyp. Die folgende Tabelle zeigt die Initialisierungswerte.  
  
|Datentyp|Standardwert|  
|---|---|  
|Alle numerischen Typen (einschließlich `Byte` und `SByte`)|0|  
|`Char`|Binäre 0|  
|Alle Verweistypen (einschließlich `Object`, `String`, und alle Arrays)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|12:00 Uhr am 1. Januar des Jahres 1 (01/01/0001 12:00:00 Uhr)|  
  
 Jedes Element einer Struktur wird initialisiert, als handele es sich um eine separate Variable. Wenn Sie die Länge eines Arrays deklariert, aber seine Elemente nicht initialisieren, wird jedes Element initialisiert, als handele es sich um eine separate Variable.  
  
## <a name="static-local-variable-lifetime"></a>Lebensdauer der statischen lokalen Variablen  
 Ein `Static` lokale Variable verfügt über eine längere Lebensdauer als die Prozedur, die in der sie deklariert ist. Die Grenzen der Lebensdauer der Variablen ist davon abhängig, in die Prozedur deklariert wird und ob es sich handelt `Shared`.  
  
|Prozedurdeklaration|Variable ist initialisiert|Variable beendet vorhandene|  
|---|---|---|  
|In einem Modul|Das erste Mal wird die Prozedur aufgerufen.|Wenn das Programm die Ausführung beendet.|  
|In einer Klasse oder Struktur ist Prozedur `Shared`|Das erste Mal wird die Prozedur in einer bestimmten Instanz oder für die Klasse oder Struktur selbst aufgerufen|Wenn das Programm die Ausführung beendet.|  
|Ist nicht in einer Klasse oder Struktur die Prozedur `Shared`|Das erste Mal wird die Prozedur in einer bestimmten Instanz aufgerufen.|Wenn die Instanz freigegeben wird, für die Garbagecollection (GC)|  
  
## <a name="attributes-and-modifiers"></a>Attribute und -Modifizierern  
 Sie können Attribute nur für Membervariablen und nicht auf lokale Variablen anwenden. Ein Attribut trägt dazu bei Informationen zu den Metadaten der Assembly, die hat keine Bedeutung für die temporäre Speicherung, z. B. lokale Variablen.  
  
 Auf Modulebene, können Sie keine der `Static` Modifizierer, um Member Variablen zu deklarieren. Auf Prozedurebene, können keine `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, Zugriffsmodifizierern Lokale Variablen deklariert werden.  
  
 Sie können angeben, welcher Code eine Variable durch Angabe zugreifen kann ein `accessmodifier`. Standardmäßig gilt für Klassen- und Variablen (außerhalb einer Prozedur) privaten Zugriff und Strukturmembervariablen in öffentlichen Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Sie können keine Zugriffsmodifizierer für lokale Variablen (innerhalb einer Prozedur).  
  
 Sie können angeben, `WithEvents` nur auf Membervariablen und nicht auf lokale Variablen innerhalb einer Prozedur. Bei Angabe von `WithEvents`, der Datentyp der Variablen muss einen bestimmten Klassentyp sein, nicht `Object`. Sie können ein Array mit nicht deklarieren `WithEvents`. Weitere Informationen zu Ereignissen finden Sie unter [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md).  
  
> [!NOTE]
>  Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss den Namen einer Membervariablen mit dem Namen der Klasse, der Struktur oder des Moduls qualifizieren. Code außerhalb einer Prozedur oder eines Blocks kann auf alle lokalen Variablen in dieser Prozedur oder eines Blocks verweisen.  
  
## <a name="releasing-managed-resources"></a>Verwaltete Ressourcen freizugeben  
 Der Garbagecollector von .NET Framework gibt ohne zusätzliche Codierung ihrerseits verwalteten Ressourcen frei. Sie können jedoch das Verwerfen einer verwalteten Ressource nicht erst, wenn für den Garbage Collector erzwingen.  
  
 Wenn eine Klasse auf eine besonders wertvolle und knappe Ressource (z. B. eine Verbindung oder eine Datei Datenbankhandle) enthält, sollten Sie nicht warten, bis zur nächsten Garbagecollection auf eine Klasseninstanz bereinigen, die nicht mehr verwendet wird. Implementieren der <xref:System.IDisposable> Schnittstelle, um eine Möglichkeit, Ressourcen, bevor eine Garbagecollection freigegeben bereitzustellen. Macht eine Klasse, die diese Schnittstelle implementiert eine `Dispose` Methode, die aufgerufen werden kann, um wertvolle Ressourcen sofort freigegeben werden zu erzwingen.  
  
 Die `Using` Anweisung automatisiert den Prozess der Erwerb einer Ressourcenpools, eine Reihe von Anweisungen ausgeführt und dann löschen, mit der die Ressource. Allerdings muss die Ressource implementieren die <xref:System.IDisposable> Schnittstelle. Weitere Informationen finden Sie unter [using-Anweisung](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert Variablen mithilfe der `Dim` -Anweisung mit verschiedenen Optionen.  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel listet die Primzahlen zwischen 1 und 30 ein. Der Gültigkeitsbereich der lokalen Variablen wird in den Kommentaren im Code beschrieben.  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die `speedValue` Variablen auf Klassenebene deklariert ist. Die `Private` Schlüsselwort wird verwendet, um die Variable zu deklarieren. Die Variable kann zugegriffen werden, von einer Prozedur in der `Car` Klasse.  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
 [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
