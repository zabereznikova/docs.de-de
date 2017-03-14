---
title: "Declare Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Declare"
  - "vb.Lib"
  - "vb.Any"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Lib keyword"
  - "declaring procedures, Declare statement"
  - "functions [Visual Basic], function procedures"
  - "declarations, procedures"
  - "procedures, declaration"
  - "procedures, external"
  - "Alias keyword"
  - "external references, Visual Basic"
  - "DLLs, declaring procedures"
  - "Declare statement"
  - "declarations, external"
  - "Visual Basic code, Function procedures"
  - "As keyword, in Declare statement"
  - "resources [Visual Basic], declaring"
  - "Public keyword, Declare statement"
  - "platform invoke, Visual Basic external references"
  - "Sub procedures, declarations"
  - "APIs, declaring API functions"
  - "Visual Basic code, Sub procedures"
  - "Function procedures, declaring"
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Declare Statement
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Deklariert einen Verweis auf eine Prozedur, die in einer externen Datei implementiert ist.  
  
## Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ]  
' -or-  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`attributelist`|Optional.  Siehe [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Optional.  Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Optional.  Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Optional.  Gibt Informationen über Zeichensätze und die Dateisuche an.  Einer der folgenden Werte ist möglich:<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) \(Standardwert\)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Optional \(entweder muss `Sub` oder `Function` angegeben werden\).  Gibt an, dass die externe Prozedur keinen Wert zurückgibt.|  
|`Function`|Optional \(entweder muss `Sub` oder `Function` angegeben werden\).  Gibt an, dass die externe Prozedur einen Wert zurückgibt.|  
|`name`|Erforderlich.  Name dieses externen Verweises.  Weitere Informationen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Erforderlich.  Leitet eine `Lib`\-Klausel ein. Diese kennzeichnet die externe Datei \(DLL oder Coderessource\), die eine externe Prozedur enthält.|  
|`libname`|Erforderlich.  Name der Datei, die die deklarierte Prozedur enthält.|  
|`Alias`|Optional.  Gibt an, dass die zu deklarierende Prozedur in der zugehörigen Datei nicht mit dem in `name` angegebenen Namen bezeichnet werden kann.  Sie geben ihre Bezeichnung in `aliasname` an.|  
|`aliasname`|Erforderlich, wenn Sie das `Alias`\-Schlüsselwort verwenden.  Zeichenfolge, die die Prozedur in einer von zwei Formen bezeichnet:<br /><br /> Der Name für den Einstiegspunkt der Prozedur in ihrer Datei in Anführungszeichen \(`""`\)<br /><br /> \- oder \-<br /><br /> Ein Nummernzeichen \(`#`\) vor einer ganzen Zahl, die die Ordinalzahl des Einstiegspunkts der Prozedur in ihrer Datei angibt.|  
|`parameterlist`|Erforderlich, wenn die Prozedur Parameter akzeptiert.  Weitere Informationen finden Sie unter [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Erforderlich, wenn `Function` angegeben ist und `Option Strict` den Wert `On` aufweist.  Datentyp des von der Prozedur zurückgegebenen Werts.|  
  
## Hinweise  
 Zuweilen müssen Sie eine Prozedur aufrufen, die in einer Datei \(z. B. eine DLL oder eine Coderessource\) außerhalb des Projekts definiert ist.  In diesem Fall kann der Visual Basic Compiler nicht auf die Informationen zugreifen, die zum ordnungsgemäßen Aufrufen der Prozedur erforderlich sind, z. B. den Speicherort der Prozedur, ihre Identifikationsmerkmale, ihre Aufruffolge und ihren Rückgabetyp sowie den von der Prozedur für Zeichenfolgen verwendeten Zeichensatz.  Die `Declare`\-Anweisung erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 `Declare` kann nur auf Modulebene verwendet werden.  Dies bedeutet, dass der *Deklarationskontext* für einen externen Verweis eine Klasse, eine Struktur oder ein Modul sein muss und keine Quelldatei, kein Namespace, keine Schnittstelle, keine Prozedur und kein Block sein kann.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Der Standardzugriff für externe Verweise ist [Public](../../../visual-basic/language-reference/modifiers/public.md).  Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
## Regeln  
  
-   **Attribute.** Sie können Attribute auf einen externen Verweis anwenden.  Jedes angewendete Attribut wirkt sich nur im Projekt und nicht in der externen Datei aus.  
  
-   **Modifizierer.** Externe Prozeduren sind implizit [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  Sie können beim Deklarieren eines externen Verweises nicht das `Shared`\-Schlüsselwort verwenden, und Sie können den freigegebenen Status des Verweises nicht ändern.  
  
     Eine externe Prozedur kann nicht für Überschreibungen verwendet werden, keine Schnittstellenmember implementieren und keine Ereignisse behandeln.  Daher können Sie die Schlüsselwörter `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements` und `Handles` in einer `Declare`\-Anweisung nicht verwenden.  
  
-   **Name der externen Prozedur.** Sie müssen für den externen Verweis nicht einen Namen festlegen \(in `name`\), der mit dem Namen des Einstiegspunkts der Prozedur in ihrer externen Datei \(`aliasname`\) übereinstimmt.  Sie können den Namen des Einstiegspunkts mit einer `Alias`\-Klausel angeben.  Dies kann sinnvoll sein, wenn die externe Prozedur einen Namen aufweist, der mit dem Namen eines in Visual Basic reservierten Modifizierers, einer Variablen, Prozedur oder eines beliebigen anderen Programmierelements in demselben Gültigkeitsbereich übereinstimmt.  
  
    > [!NOTE]
    >  In den meisten DLLs wird bei Einstiegspunktnamen die Groß\-\/Kleinschreibung beachtet.  
  
-   **Nummer der externen Prozedur.** Stattdessen können Sie auch mit einer `Alias`\-Klausel die Ordinalzahl des Einstiegspunkts in der Exporttabelle der externen Datei angeben.  Zu diesem Zweck beginnen Sie `aliasname` mit einem Nummernzeichen \(`#`\).  Dies kann sich als sinnvoll erweisen, wenn ein bestimmtes Zeichen im Namen der externen Prozedur in Visual Basic nicht zulässig ist oder wenn die Prozedur ohne Namen aus der externen Datei exportiert wird.  
  
## Datentypregeln  
  
-   **Datentypen von Parametern.** Wenn `Option Strict` den Wert `On` aufweist, müssen Sie den Datentyp jedes Parameters in `parameterlist` angeben.  Dies kann ein beliebiger Datentyp oder der Name einer Enumeration, Struktur, Klasse oder Schnittstelle sein.  In `parameterlist` können Sie den Datentyp des an jeden Parameter zu übergebenden Arguments mit einer `As`\-Klausel angeben.  
  
    > [!NOTE]
    >  Wenn die externe Prozedur nicht für .NET Framework geschrieben wurde, müssen Sie darauf achten, dass sich die Datentypen entsprechen.  Wenn Sie z. B. einen externen Verweis auf eine Visual Basic 6.0\-Prozedur mit einem `Integer`\-Parameter \(16 Bits in Visual Basic 6.0\) deklarieren, müssen Sie das entsprechende Argument in der `Declare`\-Anweisung als `Short` festlegen, da dies in Visual Basic der 16\-Bit\-Ganzzahltyp ist.  Entsprechend weist `Long` in Visual Basic 6.0 eine andere Datenbreite auf, und `Date` wird auf andere Weise implementiert.  
  
-   **Rückgabedatentyp.** Wenn die externe Prozedur eine `Function` ist und für `Option Strict` der Wert `On` festgelegt ist, müssen Sie den Datentyp des an den aufrufenden Code zurückgegebenen Werts angeben.  Dies kann ein beliebiger Datentyp oder der Name einer Enumeration, Struktur, Klasse oder Schnittstelle sein.  
  
    > [!NOTE]
    >  Der Visual Basic\-Compiler überprüft nicht, ob die von Ihnen angegebenen Datentypen mit den Datentypen der externen Prozedur kompatibel sind.  Bei nicht übereinstimmenden Datentypen generiert die Common Language Runtime zur Laufzeit eine <xref:System.Runtime.InteropServices.MarshalDirectiveException>\-Ausnahme.  
  
-   **Standarddatentypen.** Wenn `Option Strict` den Wert `Off` aufweist und Sie den Datentyp eines Parameters in `parameterlist` nicht angeben, konvertiert der Visual Basic\-Compiler das entsprechende Argument in den [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).  Ebenso geht der Compiler davon aus, dass der Rückgabedatentyp `Object` ist, wenn Sie `returntype` nicht angeben.  
  
    > [!NOTE]
    >  Da Sie eine externe Prozedur verwenden, die möglicherweise auf einer anderen Plattform geschrieben wurde, ist es riskant, bestimmte Datentypen vorauszusetzen oder Standarddatentypen für sie zuzulassen.  Es ist weitaus sicherer, den Datentyp jedes Parameters und ggf. des Rückgabewerts anzugeben.  Dadurch wird außerdem die Lesbarkeit des Codes verbessert.  
  
## Verhalten  
  
-   **Gültigkeitsbereich.** Der Gültigkeitsbereich eines externen Verweises umfasst seine Klasse, seine Struktur oder sein Modul.  
  
-   **Lebensdauer.** Ein externer Verweis verfügt über dieselbe Lebensdauer wie die Klasse, die Struktur oder das Modul, in der bzw. dem er deklariert ist.  
  
-   **Aufrufen einer externen Prozedur.** Sie rufen eine externe Prozedur auf dieselbe Weise wie eine `Function`\-Prozedur oder eine `Sub`\-Prozedur auf, indem Sie sie in einem Ausdruck verwenden, wenn sie einen Wert zurückgibt, oder indem Sie sie in einer [Call Statement](../../../visual-basic/language-reference/statements/call-statement.md) angeben, wenn sie keinen Wert zurückgibt.  
  
     Sie übergeben Argumente an die externe Prozedur genau wie von `parameterlist` in der `Declare`\-Anweisung angegeben.  Lassen Sie außer acht, wie die Parameter ursprünglich in der externen Datei deklariert wurden.  Ebenso verwenden Sie einen Rückgabewert, sofern vorhanden, genau wie von `returntype` in der `Declare`\-Anweisung angegeben.  
  
-   **Zeichensätze.** Sie können in `charsetmodifier` angeben, wie Visual Basic Zeichenfolgen beim Aufruf der externen Prozedur marshallen soll.  Mit dem `Ansi`\-Modifizierer marshallt Visual Basic alle Zeichenfolgen in ANSI\-Werte, und mit dem `Unicode`\-Modifizierer werden alle Zeichenfolgen in Unicode\-Werte gemarshallt.  Mit dem `Auto`\-Modifizierer marshallt Visual Basic Zeichenfolgen gemäß den .NET Framework\-Regeln, die auf dem `name` des externen Verweises oder ggf. auf `aliasname` beruhen.  Der Standardwert ist `Ansi`.  
  
     `charsetmodifier` gibt auch an, wie Visual Basic die externe Prozedur innerhalb seiner externen Datei nachschlagen sollte.  `Ansi` und `Unicode` weisen Visual Basic an nachzuschlagen, ohne seinen Namen während der Suche zu ändern.  `Auto` weist Visual Basic an, den Basiszeichensatz von der Laufzeitplattform zu bestimmen und ändert möglicherweise den externen Verfahrensnamen, wie folgt:  
  
    -   Auf einer ANSI\-Plattform, z. B. Windows 95, Windows 98 oder Windows Millennium Edition, wird zunächst die externe Prozedur ohne Namensänderung gesucht.  Wenn dies fehlschlägt, wird an den Namen der externen Prozedur "A" angefügt und die Suche wiederholt.  
  
    -   Auf einer Unicode\-Plattform, z. B. Windows NT, Windows 2000 oder Windows XP, wird zunächst die externe Prozedur ohne Namensänderung gesucht.  Wenn dies fehlschlägt, wird an den Namen der externen Prozedur "W" angefügt und die Suche wiederholt.  
  
-   **Mechanismus.** Visual Basic verwendet den Mechanismus des *Plattformaufrufs* \(PInvoke\) von .NET Framework, um externe Prozeduren aufzulösen und auf sie zuzugreifen.  Sowohl die `Declare`\-Anweisung als auch die <xref:System.Runtime.InteropServices.DllImportAttribute>\-Klasse verwenden diesen Mechanismus automatisch, und Sie benötigen keine Kenntnisse über PInvoke.  Weitere Informationen finden Sie unter [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Wenn die externe Prozedur außerhalb der Common Language Runtime \(CLR\) ausgeführt wird, handelt es sich um *nicht verwalteten Code*.  Bei dem Aufruf einer solchen Prozedur, z. B. einer Win32\-API\-Funktion oder einer COM\-Methode, setzen Sie die Anwendung möglicherweise einem Sicherheitsrisiko aus.  Weitere Informationen finden Sie unter [Secure Coding Guidelines for Unmanaged Code](../Topic/Secure%20Coding%20Guidelines%20for%20Unmanaged%20Code.md).  
  
## Beispiel  
 Im folgenden Beispiel wird ein externer Verweis auf eine `Function`\-Prozedur deklariert, die den aktuellen Benutzernamen zurückgibt.  Anschließend wird die externe Prozedur `GetUserNameA` als Bestandteil der `getUser`\-Prozedur aufgerufen.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_1.vb)]  
  
## Beispiel  
 Das <xref:System.Runtime.InteropServices.DllImportAttribute> bietet eine alternative Möglichkeit der Verwendung von Funktionen in nicht verwaltetem Code.  Im folgenden Beispiel wird eine importierte Funktion ohne Verwendung einer `Declare`\-Anweisung deklariert.  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_3.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>   
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Call Statement](../../../visual-basic/language-reference/statements/call-statement.md)   
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)