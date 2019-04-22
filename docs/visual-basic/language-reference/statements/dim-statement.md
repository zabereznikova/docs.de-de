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
ms.openlocfilehash: cab1cc07d23a44e57bdb0962a323b014308cb1e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836557"
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
  
     Dies ist optional. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `accessmodifier`  
  
     Dies ist optional. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [Protected Friend](../../language-reference/modifiers/protected-friend.md)
    
    - [Private Protected](../../language-reference/modifiers/private-protected.md)

     Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `Shared`  
  
     Dies ist optional. Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Dies ist optional. Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Static`  
  
     Dies ist optional. Finden Sie unter [statische](../../../visual-basic/language-reference/modifiers/static.md).  
  
-   `ReadOnly`  
  
     Dies ist optional. Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WithEvents`  
  
     Dies ist optional. Gibt an, dass diese Objektvariablen, die auf Instanzen einer Klasse zu verweisen, die Ereignisse auslösen kann. Finden Sie unter [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).  
  
-   `variablelist`  
  
     Erforderlich. Liste der Variablen, die in dieser Anweisung deklariert wird.  
  
     `variable [ , variable ... ]`  
  
     Jede `variable` weist folgende Syntax und Bestandteile auf:  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`variablename`|Erforderlich. Name der Variablen. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
    |`boundslist`|Dies ist optional. Liste der Grenzen der einzelnen Dimensionen des Arrayvariable.|  
    |`New`|Dies ist optional. Erstellt eine neue Instanz der Klasse bei der `Dim` Anweisung wird ausgeführt.|  
    |`datatype`|Dies ist optional. Der Datentyp der Variablen.|  
    |`With`|Dies ist optional. Führt der Objektinitialisiererliste.|  
    |`propertyname`|Dies ist optional. Der Name einer Eigenschaft in der Klasse nutzen Sie eine Instanz von.|  
    |`propinitializer`|Nach dem erforderlichen `propertyname` =. Der Ausdruck, der ausgewertet und auf den Eigenschaftennamen zugewiesen wird.|  
    |`initializer`|Optional, wenn `New` nicht angegeben ist. Ein Ausdruck, der ausgewertet und bei der Erstellung der Variablen zugewiesen.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Basic-Compiler verwendet die `Dim` Anweisung, um zu bestimmen, die Variable den Datentyp und andere Informationen, z. B. welcher Code auf die Variable zugreifen kann. Das folgende Beispiel deklariert eine Variable für ein `Integer` Wert.  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 Für einen Verweistyp handelt, Sie verwenden die `New` Schlüsselwort, um eine neue Instanz der Klasse zu erstellen oder eine Struktur, die durch den-Datentyp angegeben ist. Bei Verwendung von `New`, verwenden Sie einen Initialisiererausdruck nicht. Stattdessen geben Sie Argumente, wenn erforderlich, an den Konstruktor der Klasse sind von denen Sie die Variable erstellen.  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 Sie können eine Variable in einer Prozedur, blockieren, Klasse, Struktur oder Modul deklarieren. Sie können eine Variable in einer Quelldatei, Namespace oder Schnittstelle nicht deklarieren. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Eine Variable, die auf Modulebene außerhalb einer Prozedur, deklariert ist ist eine *Membervariable* oder *Feld*. Membervariablen sind in der gesamten die Klasse, Struktur oder Modul. Eine Variable, die auf Prozedurebene deklariert wird ist eine *lokale Variable*. Lokale Variablen sind nur in die Prozedur oder eines Blocks.  
  
 Die folgenden Zugriffsmodifizierer zum Deklarieren von Variablen, die außerhalb einer Prozedur verwendet werden: `Public`, `Protected`, `Friend`, `Protected Friend`, und `Private`. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Die `Dim` Schlüsselwort ist optional und in der Regel weggelassen wird, wenn Sie einen der folgenden Modifizierer angeben: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, oder `WithEvents`.  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 Wenn `Option Explicit` ist aktiviert (Standard), erfordert der Compiler eine Deklaration für jede Variable, die Sie verwenden. Weitere Informationen finden Sie unter [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md).  
  
## <a name="specifying-an-initial-value"></a>Geben Sie einen anfänglichen Wert  
 Sie können einen Wert einer Variablen zuweisen, bei der Erstellung. Für einen Werttyp handelt, Sie verwenden eine *Initialisierer* , geben Sie einen Ausdruck, der Variablen zugewiesen werden soll. Der Ausdruck muss mit einer Konstante ausgewertet werden, die zur Kompilierzeit berechnet werden kann.  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 Wenn ein Initialisierer angegeben ist, und ein Datentyp nicht, in angegeben ist eine `As` -Klausel *Typrückschluss* wird verwendet, um den Datentyp aus dem Initialisierer abzuleiten. Im folgenden Beispiel beide `num1` und `num2` sind stark typisiert, als ganze Zahlen. In der zweiten Deklaration leitet der Typrückschluss den Typ aus dem Wert 3.  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 Typrückschluss ist auf Prozedurebene gültig. Es gilt nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle. Weitere Informationen zu den Typrückschluss, finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Informationen darüber, was geschieht, wenn einer/m / -Datentyp nicht angegeben ist, finden Sie unter [-Standarddatentypen und-Werte](../../../visual-basic/language-reference/statements/dim-statement.md#default) weiter unten in diesem Thema.  
  
 Sie können eine *Objektinitialisierer* um Instanzen von benannten und anonymen Typen zu deklarieren. Der folgende Code erstellt eine Instanz von einem `Student` Klasse und verwendet Sie einen Objektinitialisierer, um Eigenschaften zu initialisieren.  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 Weitere Informationen über Objektinitialisierer finden Sie unter [Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), und [anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="declaring-multiple-variables"></a>Deklarieren Sie mehrere Variablen  
 Sie können mehrere Variablen in einer deklarationsanweisung, deklarieren, der Variablenname, der für jede einzelne und den nachfolgenden jedes Arrayname in Klammern angeben. Mehrere Variablen werden durch Kommas voneinander getrennt.  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 Wenn Sie mehr als eine Variable mit einem deklarieren `As` -Klausel kann keinen Initialisierer für diese Gruppe von Variablen nicht bereitstellen.  
  
 Sie können unterschiedliche Datentypen für verschiedene Variablen angeben, über ein separates `As` -Klausel für jede Variable, die Sie deklarieren. Jede Variable wird in der ersten angegebenen Datentyp `As` -Klausel nach dem die `variablename` Teil.  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>Arrays  
 Sie können eine Variable für deklarieren eine *Array*, die mehrere Werte enthalten kann. Um anzugeben, dass eine Variable ein Array enthält, führen Sie die `variablename` sofort mit Klammern. Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Sie können die untere und obere Grenze jeder Dimension eines Arrays angeben. Um dies zu erreichen, fügen einen `boundslist` innerhalb der Klammern. Für jede Dimension die `boundslist` gibt an, die obere Grenze und optional die untere Grenze. Die Untergrenze ist immer 0 (null), ob Sie es angeben. Jeder Index kann von 0 (null), durch den Wert der oberen Grenze variieren.  
  
 Die folgenden beiden Anweisungen sind gleichwertig. Jede Anweisung deklariert ein Array von 21 `Integer` Elemente. Wenn Sie das Array zugreifen, kann der Index von 0 bis 20 variieren.  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 Die folgende Anweisung deklariert ein zweidimensionales Array vom Typ `Double`. Das Array hat 4 Zeilen (3 + 1) der 6 Spalten (5 + 1). Beachten Sie, dass eine Obergrenze den höchsten möglichen Wert für den Index, nicht die Länge der Dimension darstellt. Die Länge der Dimension ist die obere Grenze plus eins.  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 Ein Array kann von 1 bis 32 Dimensionen aufweisen.  
  
 Sie können alle Grenzen in eine Arraydeklaration leer lassen. Wenn Sie dies tun, das Array hat die Anzahl der Dimensionen, die Sie angeben, aber es ist nicht initialisiert. Es hat den Wert `Nothing` bis Sie über mindestens initialisieren einige seiner Elemente. Die `Dim` -Anweisung muss entweder Grenzen für alle Dimensionen oder für keine Dimensionen angegeben.  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 Wenn das Array mehr als eine Dimension hat, müssen Sie Kommas zwischen die Klammern an, dass die Anzahl der Dimensionen einschließen.  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 Sie können deklarieren, ein *Array der Länge 0 (null)* durch deklarieren eine der Dimensionen des Arrays -1 sein. Eine Variable, ein Array der Länge 0 (null) enthält, keinen Wert `Nothing`. Arrays mit der Länge 0 (null) sind bestimmte Funktionen der common Language Runtime erforderlich. Wenn Sie versuchen, ein entsprechendes Array zugreifen, tritt eine Ausnahme zur Laufzeit. Weitere Informationen finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Sie können die Werte eines Arrays mit einem Arrayliteral initialisieren. Umschließen Sie zu diesem Zweck die Initialisierungswerte mit geschweiften Klammern (`{}`).  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 Für mehrdimensionale Arrays wird die Initialisierung für jede separate Dimension in geschweiften Klammern in der äußeren Dimension eingeschlossen. Die Elemente werden in zeilengerichteter Reihenfolge angegeben.  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 Weitere Informationen zu den Array-Literale, finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="default"></a> Standarddatentypen und-Werte  
 Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.  
  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|---|---|---|---|  
|Nein|Nein|`Dim qty`|Wenn [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) ist off (Standardeinstellung), die Variable festgelegt ist, um `Nothing`.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|  
|Nein|Ja|`Dim qty = 5`|Wenn [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) ist (Standardeinstellung), geben Sie die Variable verwendet die Daten des Initialisierers. Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Siehe Tabelle weiter unten in diesem Abschnitt.|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|  
  
 Wenn Sie einen Datentyp angeben, aber Sie einen Initialisierer nicht geben, initialisiert die Visual Basic die Variable auf den Standardwert für seinen Datentyp. Die folgende Tabelle zeigt die Initialisierungswerte.  
  
|Datentyp|Standardwert|  
|---|---|  
|Alle numerischen Typen (einschließlich `Byte` und `SByte`)|0|  
|`Char`|Binäre 0|  
|Alle Referenztypen (einschließlich `Object`, `String`, und alle Arrays)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|12:00 Uhr des 1. Januar des Jahres 1 (01/01/0001 12:00:00 Uhr)|  
  
 Jedes Element einer Struktur wird initialisiert, als handele es sich um eine separate Variable. Wenn Sie die Länge eines Arrays deklarieren, aber die Elemente nicht initialisieren, wird jedes Element initialisiert, als handele es sich um eine separate Variable.  
  
## <a name="static-local-variable-lifetime"></a>Lebensdauer der statischen lokalen Variablen  
 Ein `Static` lokale Variable hat eine längere Lebensdauer als die Prozedur, die in der sie deklariert ist. Die Grenzen der die Lebensdauer der Variablen ist davon abhängig, in die Prozedur deklariert wird und ob es sich handelt `Shared`.  
  
|Deklaration der Prozedur|Variable ist initialisiert|Variable beendet vorhandene|  
|---|---|---|  
|In einem Modul|Beim ersten wird die Prozedur aufgerufen.|Wenn Ihr Programm die Ausführung angehalten wird|  
|In einer Klasse oder Struktur ist Prozedur `Shared`|Beim ersten wird die Prozedur auf eine bestimmte Instanz oder auf die Klasse oder Struktur selbst aufgerufen|Wenn Ihr Programm die Ausführung angehalten wird|  
|Ist nicht in einer Klasse oder Struktur die Prozedur `Shared`|Beim ersten wird die Prozedur in einer bestimmten Instanz aufgerufen.|Wenn die Instanz für die Garbagecollection (GC) freigegeben wird|  
  
## <a name="attributes-and-modifiers"></a>Attribute und Modifizierer  
 Sie können Attribute anwenden, nur Membervariablen, nicht für lokale Variablen. Ein Attribut fügt Informationen an den Metadaten der Assembly, die hat keine Bedeutung für die temporäre Speicherung, z. B. lokale Variablen.  
  
 Sie können nicht auf Modulebene verwenden die `Static` Modifizierer zum Deklarieren von Variablen Member. Auf Prozedurebene, können keine `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, Zugriffsmodifizierern Lokale Variablen deklariert werden.  
  
 Sie können angeben, welcher Code eine Variable durch Angabe zugreifen kann ein `accessmodifier`. -Klasse Variablen (außerhalb einer Prozedur) standardmäßig und in privaten Zugriff und Strukturmembervariablen in öffentlichen Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Sie können keine Zugriffsmodifizierer für lokale Variablen (innerhalb einer Prozedur).  
  
 Sie können angeben, `WithEvents` nur für die Membervariablen und nicht für lokale Variablen innerhalb einer Prozedur. Bei Angabe von `WithEvents`, der Datentyp der Variablen muss einen bestimmten Klassentyp nicht `Object`. Sie können nicht deklarieren ein Array mit `WithEvents`. Weitere Informationen zu Ereignissen finden Sie unter [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md).  
  
> [!NOTE]
>  Code außerhalb einer Klasse, einer Struktur oder das Modul muss eine Membervariable den Namen durch den Namen dieser Klasse, Struktur oder Modul qualifizieren. Code außerhalb einer Prozedur oder einem Block kann auf alle lokalen Variablen in dieser Prozedur oder eines Blocks verweisen.  
  
## <a name="releasing-managed-resources"></a>Freigeben von verwalteten Ressourcen  
 Der Garbagecollector von .NET Framework gibt ohne zusätzliche Programmierkenntnisse ihrerseits verwalteten Ressourcen frei. Allerdings können Sie die Freigabe einer verwalteten Ressource anstatt abzuwarten, bis der Garbage Collection erzwingen.  
  
 Wenn eine Klasse auf eine besonders nützliche und knappe Ressource (z. B. eine Datenbank-Verbindung oder die Dateihandle) enthält, möchten Sie nicht warten, bis die nächste Garbagecollection zum Bereinigen der Instanz einer Klasse, die nicht mehr verwendet wird. Implementieren der <xref:System.IDisposable> Schnittstelle, um die Möglichkeit, Ressourcen, bevor eine Garbagecollection freigegeben. Stellt eine Klasse, die diese Schnittstelle implementiert einen `Dispose` -Methode, die aufgerufen werden kann, um wertvolle Ressourcen sofort freigegeben werden zu erzwingen.  
  
 Die `Using` Anweisung automatisiert den Prozess der Erwerb einer Ressourcensatzes, eine Reihe von Anweisungen ausgeführt und dann die Ressource freigegeben. Allerdings muss die Ressource implementieren die <xref:System.IDisposable> Schnittstelle. Weitere Informationen finden Sie unter [using-Anweisung](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert Variablen mithilfe der `Dim` -Anweisung mit verschiedenen Optionen.  
  
 [!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel listet die Primzahlen zwischen 1 und 30. Der Bereich der lokalen Variablen wird in den Kommentaren im Code beschrieben.  
  
 [!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die `speedValue` Variable auf Klassenebene deklariert wird. Die `Private` -Schlüsselwort wird verwendet, um die Variable zu deklarieren. Die Variable kann zugegriffen werden, von einer Prozedur in der `Car` Klasse.  
  
 [!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]  
  
 [!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]  
  
## <a name="see-also"></a>Siehe auch

- [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)
- [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
