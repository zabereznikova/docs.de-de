---
title: Dim-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Dim
- Dim
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, in Dim statement
- Dim statement
- fixed-length strings, declaring
- variables [Visual Basic], declaring
- WithEvents keyword, Dim statement
- dynamic arrays, Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields, as member variables
- declarations, dynamic arrays
- member variables
- default values
- data types [Visual Basic], assigning
- braces {}
- As keyword, in Dim statement
- arrays [Visual Basic], declaring
- New keyword, Dim statement
- To keyword, in Dim statement
- storage, allocating
- local variables
- declaration statements
- Dim statement, syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
caps.latest.revision: 72
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 00d5d0e83a88a0c7ac3ade92d09c584fce64fcd8
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

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
  
     Optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `accessmodifier`  
  
     Optional. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `Shared`  
  
     Optional. Finden Sie unter [freigegebenen](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Static`  
  
     Optional. Finden Sie unter [statische](../../../visual-basic/language-reference/modifiers/static.md).  
  
-   `ReadOnly`  
  
     Optional. Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WithEvents`  
  
     Optional. Gibt an, dass diese Objektvariablen, die auf Instanzen einer Klasse verweisen, die Ereignisse auslösen kann. Finden Sie unter [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).  
  
-   `variablelist`  
  
     Erforderlich. Liste der Variablen, die in dieser Anweisung deklariert werden.  
  
     `variable [ , variable ... ]`  
  
     Jede `variable` weist folgende Syntax und Bestandteile auf:  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`variablename`|Erforderlich. Name der Variablen Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
    |`boundslist`|Optional. Liste der Grenzen jeder Dimension einer Arrayvariablen.|  
    |`New`|Optional. Erstellt eine neue Instanz der Klasse bei der `Dim` Anweisung wird ausgeführt.|  
    |`datatype`|Optional. Der Datentyp der Variablen.|  
    |`With`|Optional. Führt die Objektinitialisiererliste.|  
    |`propertyname`|Optional. Der Name einer Eigenschaft in der Klasse wird eine Instanz erstellt.|  
    |`propinitializer`|Nach dem erforderlichen `propertyname` =. Der Ausdruck, der ausgewertet und dem Eigenschaftennamen zugewiesen wird.|  
    |`initializer`|Optional, wenn `New` nicht angegeben ist. Ein Ausdruck, der ausgewertet und bei der Erstellung der Variablen zugewiesen.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Basic-Compiler verwendet die `Dim` Anweisung ermittelt Datentyp der Variablen und andere Informationen, z. B. welcher Code auf die Variable zugreifen kann. Das folgende Beispiel deklariert eine Variable für ein `Integer` Wert.  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 Für einen Verweistyp handelt, verwenden Sie die `New` -Schlüsselwort zum Erstellen einer neuen Instanz der Klasse oder Struktur, die durch den Datentyp angegeben ist. Bei Verwendung von `New`, verwenden Sie einen Initialisierungsausdruck. Stattdessen geben Sie Argumente, falls erforderlich, an den Konstruktor der Klasse aus der Sie die Variable erstellen.  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 Sie können eine Variable in einer Prozedur, Block, Klasse, Struktur oder Modul deklarieren. Sie können eine Variable in einer Quelldatei, den Namespace oder die Schnittstelle nicht deklarieren. Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Eine auf Modulebene außerhalb einer Prozedur deklarierte Variable ist eine *Membervariable* oder *Feld*. Membervariable zur ihrer Klasse, Struktur oder Modul der Gültigkeitsbereich. Eine auf Prozedurebene deklarierte Variable ist eine *lokale Variable*. Lokale Variablen sind nur innerhalb ihrer Prozedur oder eines Blocks.  
  
 Die folgenden Zugriffsmodifizierer werden zum Deklarieren von Variablen außerhalb einer Prozedur verwendet: `Public`, `Protected`, `Friend`, `Protected Friend`, und `Private`. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Die `Dim` Schlüsselwort ist optional und in der Regel weggelassen, wenn Sie einen der folgenden Modifizierer angeben: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, oder `WithEvents`.  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 Wenn `Option Explicit` ist (Standard), erfordert der Compiler eine Deklaration für jede Variable, die Sie verwenden. Weitere Informationen finden Sie unter [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md).  
  
## <a name="specifying-an-initial-value"></a>Festlegen eines Anfangswerts  
 Sie können einer Variablen einen Wert zuweisen, wenn er erstellt wird. Für einen Werttyp handelt, Sie verwenden ein *Initialisierer* , geben Sie einen Ausdruck, der Variablen zugewiesen werden soll. Der Ausdruck muss eine Konstante ergeben, der zur Kompilierungszeit berechnet werden kann.  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 Wenn ein Initialisierer angegeben ist und ein Datentyp nicht, in angegeben ist einer `As` -Klausel, *Typrückschluss* wird verwendet, um den Datentyp aus der Initialisierung abzuleiten. Im folgenden Beispiel beide `num1` und `num2` sind stark typisiert als ganze Zahlen. In der zweiten Deklaration leitet der Typrückschluss den Typ aus dem Wert 3.  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 Typrückschluss ist auf der Prozedurebene gültig. Sie gilt nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle. Weitere Informationen zu den Typrückschluss, finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [lokalen Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Informationen darüber, was geschieht, wenn ein Datentyp oder eine Initialisierung nicht angegeben ist, finden Sie unter [Standard-Datentypen und Werte](../../../visual-basic/language-reference/statements/dim-statement.md#default) weiter unten in diesem Thema.  
  
 Können Sie eine *-Objekt Initialisierer* Instanzen von benannten und anonymen Typen zu deklarieren. Der folgende Code erstellt eine Instanz einer `Student` -Klasse und verwendet einen Objektinitialisierer, um Eigenschaften zu initialisieren.  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 Weitere Informationen über Objektinitialisierer finden Sie unter [Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Objektinitialisierer: benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), und [anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="declaring-multiple-variables"></a>Mehrere Variablen zu deklarieren  
 Sie können mehrere Variablen in einer Deklaration-Anweisung deklarieren, die den Variablennamen jeweils und nach jeder Arrayname in Klammern angegeben. Mehrere Variablen werden durch Kommas voneinander getrennt.  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 Wenn Sie mehrere Variablen mit einem deklarieren `As` -Klausel kann einen Initialisierer für diese Gruppe von Variablen nicht bereitstellen.  
  
 Sie können für verschiedene Variablen unterschiedliche Datentypen angeben, indem Sie eine separate `As` -Klausel für jede Variable, die Sie deklarieren. Jede Variable übernimmt den Datentyp, der in der ersten angegebenen `As` -Klausel nach seiner `variablename` Teil.  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>Arrays  
 Deklarieren Sie eine Variable zum Speichern einer *Array*, die mehrere Werte enthalten kann. Um anzugeben, dass eine Variable ein Array enthält, führen Sie die `variablename` Klammern. Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Sie können die unter- und Obergrenze jeder Dimension eines Arrays angeben. Dazu gehören ein `boundslist` innerhalb der Klammern. Für jede Dimension die `boundslist` gibt die Obergrenze und optional die Untergrenze. Die untere Grenze ist immer&0;, ob Sie es angeben. Jeder Index kann zwischen&0; (null) und dem Wert seiner Obergrenze betragen.  
  
 Die beiden folgenden Anweisungen sind gleichwertig. Jede Anweisung deklariert ein Array von 21 `Integer` Elemente. Wenn Sie das Array zugreifen, kann der Index von 0 bis 20 variieren.  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 Die folgende Anweisung deklariert ein zweidimensionales Array vom Typ `Double`. Das Array weist 4 Zeilen (3 + 1) der 6 Spalten (5 + 1) jeder. Beachten Sie, dass eine Obergrenze den höchsten möglichen Wert für den Index, nicht die Länge der Dimension darstellt. Die Länge der Dimension ist die Obergrenze plus eins.  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 Ein Array kann von 1 bis 32 Dimensionen aufweisen.  
  
 Sie können alle Grenzen in der Arraydeklaration eines weglassen. Wenn Sie dies tun, das Array enthält die Anzahl der Dimensionen, die Sie angeben, aber nicht initialisiert ist. Hat es den Wert von `Nothing` bis Sie mindestens initialisieren einige seiner Elemente. Die `Dim` -Anweisung müssen entweder Grenzen für alle Dimensionen oder für keine Dimensionen angegeben.  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 Wenn das Array mehr als eine Dimension hat, müssen Sie zwischen den Klammern Kommas an, dass die Anzahl der Dimensionen einschließen.  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 Können Sie deklarieren eine *Array der Länge&0;* durch deklarieren eine der Dimensionen des Arrays als-1 sein. Eine Variable, die ein Array der Länge&0; (null) enthält, verfügt nicht über den Wert `Nothing`. Arrays mit der Länge&0; (null) sind bestimmte Funktionen der common Language Runtime erforderlich. Wenn Sie versuchen, ein solches Array zuzugreifen, tritt eine Ausnahme zur Laufzeit. Weitere Informationen finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Sie können die Werte eines Arrays mit einem Arrayliteral initialisieren. Hierzu setzen Sie die Initialisierungswerte in geschweifte Klammern (`{}`).  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 Bei mehrdimensionalen Arrays wird die Initialisierung jeder einzelnen Dimension in geschweifte Klammern innerhalb der äußeren Dimension eingeschlossen. Die Elemente werden in zeilengerichteter Reihenfolge angegeben.  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 Weitere Informationen über Arrayliterale finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
##  <a name="default"></a>Standarddatentypen und-Werte  
 Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.  
  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|---|---|---|---|  
|Nein|Nein|`Dim qty`|Wenn [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) ist off (Standardeinstellung), die Variable festgelegt ist, um `Nothing`.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Nein|Ja|`Dim qty = 5`|Wenn [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) ist (Standard), übernimmt die Variable den Datentyp des Initialisierers. Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Siehe die Tabelle weiter unten in diesem Abschnitt.|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|  
  
 Wenn Sie einen Datentyp angeben, aber Sie einen Initialisierer geben [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] die Variable auf den Standardwert für seinen Datentyp initialisiert. Die folgende Tabelle zeigt die Initialisierungswerte.  
  
|Datentyp|Standardwert|  
|---|---|  
|Alle numerischen Typen (einschließlich `Byte` und `SByte`)|0|  
|`Char`|Binäre 0|  
|Alle Referenztypen (einschließlich `Object`, `String`, und alle Arrays)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|12:00 Uhr des 1. Januar des Jahres 1 (01/01/0001 12:00:00 Uhr)|  
  
 Jedes Element einer Struktur wird wie eine separate Variable initialisiert. Wenn Sie die Länge eines Arrays deklarieren, aber seine Elemente nicht initialisieren, wird jedes Element wie eine separate Variable initialisiert.  
  
## <a name="static-local-variable-lifetime"></a>Lebensdauer der statischen lokalen Variablen  
 Ein `Static` lokale Variable hat eine längere Lebensdauer als die Prozedur, in der sie deklariert ist. Die Grenzen der Lebensdauer der Variablen ist davon abhängig, wo die Prozedur deklariert wird und ob es ist `Shared`.  
  
|Deklaration der Prozedur|Variable initialisiert|Variable beendet vorhandene|  
|---|---|---|  
|In einem Modul|Das erste Mal wird die Prozedur aufgerufen.|Wenn das Programm die Ausführung beendet|  
|Verfahren ist in einer Klasse oder Struktur`Shared`|Das erste Mal ist das Verfahren für eine bestimmte Instanz oder für die Klasse oder Struktur selbst aufgerufen|Wenn das Programm die Ausführung beendet|  
|Ist nicht in einer Klasse oder Struktur die Prozedur`Shared`|Beim ersten der Prozedur für eine bestimmte Instanz Aufruf|Wenn die Instanz für die Garbagecollection (GC) freigegeben wird|  
  
## <a name="attributes-and-modifiers"></a>Attribute und Modifizierer  
 Sie können Attribute nur auf Membervariablen und nicht auf lokale Variablen anwenden. Ein Attribut fügt die Informationen in den Metadaten der Assembly, die hat keine Bedeutung für die temporäre Speicherung wie z. B. lokale Variablen.  
  
 Auf Modulebene können keine der `Static` Modifizierer Element Variablen deklarieren. Auf Prozedurebene können keine `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, Zugriffsmodifizierern, lokale Variablen zu deklarieren.  
  
 Sie können angeben, welcher Code auf eine Variable durch Angabe zugreifen kann ein `accessmodifier`. Standardmäßig gilt für Klassen- und Variablen (außerhalb einer Prozedur) privater Zugriff und Strukturmembervariablen in öffentlichen Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Sie können keine Zugriffsmodifizierer für lokale Variablen (in einer Prozedur).  
  
 Sie können angeben, `WithEvents` nur für Membervariablen und nicht für lokale Variablen in einer Prozedur. Bei Angabe von `WithEvents`, der Datentyp der Variablen muss einen bestimmten Klassentyp, nicht `Object`. Sie können nicht deklarieren ein Arrays mit `WithEvents`. Weitere Informationen zu Ereignissen finden Sie unter [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md).  
  
> [!NOTE]
>  Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss den Namen eine Membervariable mit dem Namen der Klasse, der Struktur oder des Moduls qualifizieren. Code außerhalb einer Prozedur oder eines Blocks kann auf keine lokalen Variablen innerhalb dieser Prozedur bzw. Blocks verweisen.  
  
## <a name="releasing-managed-resources"></a>Verwaltete Ressourcen freizugeben  
 Der Garbagecollector von .NET Framework frei verwalteten Ressourcen ohne zusätzliche Codierung ihrerseits. Sie können jedoch das Verwerfen einer verwalteten Ressource anstatt zu warten, dass der Garbage Collector erzwingen.  
  
 Wenn eine Klasse auf eine besonders nützliche und knappe Ressource (z. B. einen Datenbank-Verbindung oder Datei-Handle) enthält, möchten Sie nicht warten, bis zur nächsten Garbagecollection auf, um eine Instanz der Klasse zu bereinigen, die nicht mehr verwendet wird. Implementieren der <xref:System.IDisposable>Schnittstelle, um eine Möglichkeit, Ressourcen vor einer Garbagecollection freigegeben.</xref:System.IDisposable> Stellt eine Klasse, die diese Schnittstelle implementiert eine `Dispose` Methode, die aufgerufen werden kann, um wertvolle Ressourcen sofort freigegeben werden zu erzwingen.  
  
 Die `Using` Anweisung automatisiert den Prozess der Erwerb einer Ressourcenpools, eine Gruppe von Anweisungen ausgeführt und dann die Ressource freigegeben. Allerdings muss die Ressource implementieren die <xref:System.IDisposable>Schnittstelle.</xref:System.IDisposable> Weitere Informationen finden Sie unter [Using-Anweisung](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert Variablen mithilfe der `Dim` -Anweisung mit verschiedenen Optionen.  
  
 [!code-vb[VbVbalrStatements&#141;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel listet die Primzahlen zwischen 1 und 30. Der Bereich der lokalen Variablen wird in den Kommentaren im Code beschrieben.  
  
 [!code-vb[VbVbalrStatements&#142;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die `speedValue` Variable auf Klassenebene deklariert wird. Das `Private` -Schlüsselwort wird verwendet, um die Variable zu deklarieren. Die Variable kann von einer beliebigen Prozedur zugegriffen werden die `Car` Klasse.  
  
 [!code-vb[VbVbalrStatements&#144;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements&#145;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)   
 [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)   
 [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)   
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

