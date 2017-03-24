---
title: 'Exemplarische Vorgehensweise: Aufrufen von Windows-APIs (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls, walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement, declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5001ccebb0a5b8cadd4e856342601506cf1d033f
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Exemplarische Vorgehensweise: Aufrufen von Windows-APIs (Visual Basic)
Windows-APIs sind Dynamic Link Libraries (DLLs), die Teil des Windows-Betriebssystems sind. Sie verwenden, um Aufgaben auszuführen, wenn es schwierig, eine eigene Prozeduren zu schreiben ist. Windows enthält z. B. eine Funktion namens `FlashWindowEx` , mit der Sie die Titelleiste für eine Anwendung zwischen helle und dunkle Farbtöne.  
  
 Der Vorteil der Verwendung von Windows-APIs in Ihrem Code ist, dass sie Entwicklungszeit sparen, da sie enthalten zahlreiche nützliche Funktionen, die bereits geschrieben werden und darauf warten, verwendet werden. Der Nachteil besteht darin, dass Windows-APIs arbeiten mit und fehleranfällig, wenn etwas schief geht, schwierig sein kann.  
  
 Windows-APIs stellen eine besondere Kategorie der Interoperabilität dar. Windows-APIs verwenden keinen verwalteten Code, verfügen nicht über integrierte Typbibliotheken und Verwenden von Datentypen, die nicht mit denen in Visual Studio unterscheiden. Aufgrund dieser Unterschiede und weil Windows-APIs keine COM-Objekte, Interoperabilität mit Windows-APIs sind und die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] erfolgt unter Verwendung der Plattform aufrufen, oder PInvoke. Der Plattformaufruf ist ein Dienst, wodurch verwalteter Code zum Aufrufen von nicht verwalteter Funktionen in DLLs implementiert. Weitere Informationen finden Sie unter [verwenden nicht verwalteter DLL-Funktionen](http://msdn.microsoft.com/library/eca7606e-ebfb-4f47-b8d9-289903fdc045). Können PInvoke in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] mithilfe der `Declare` -Anweisung oder durch Anwenden der `DllImport` -Attribut auf eine leere Prozedur.  
  
 Windows-API-Aufrufe sind ein wichtiger Teil der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programmierung in der Vergangenheit, jedoch sind selten notwendig mit [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]. Wann immer möglich, sollten Sie aus verwalteten Code verwenden die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Aufgaben anstelle von Windows-API-Aufrufe. Diese exemplarische Vorgehensweise enthält Informationen über die Situationen, in denen die Verwendung von Windows-APIs erforderlich ist.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="api-calls-using-declare"></a>Deklarieren von API-Aufrufe mit  
 Die gängigste Methode zum Aufrufen von Windows-APIs ist in der `Declare` Anweisung.  
  
#### <a name="to-declare-a-dll-procedure"></a>Deklarieren Sie eine DLL-Prozedur  
  
1.  Bestimmen Sie den Namen der Funktion, die Sie aufrufen möchten, sowie die Argumente, Argumenttypen und zurückgeben Sie-Wert als auch den Namen und Speicherort der DLL, die er enthält.  
  
    > [!NOTE]
    >  Ausführliche Informationen über Windows-APIs finden Sie unter der Win32-SDK-Dokumentation in der Platform SDK-Windows-API. Weitere Informationen über die Konstanten, die Windows-APIs verwenden, überprüfen Sie die Headerdateien, z. B. Windows.h im Plattform-SDK enthalten.  
  
2.  Öffnen Sie ein neues Windows-Anwendungsprojekt, indem Sie auf **neu** auf der **Datei** Menü und dann auf **Projekt**. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Wählen Sie **Windows-Anwendung** aus der Liste der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Projektvorlagen. Das neue Projekt wird angezeigt.  
  
4.  Fügen Sie die folgenden `Declare` Funktion entweder auf die Klasse oder das Modul, in dem Sie die DLL verwenden möchten:  
  
     [!code-vb[VbVbalrInterop&#9;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>Teile der Declare-Anweisung  
 Die `Declare` -Anweisung enthält die folgenden Elemente.  
  
#### <a name="auto-modifier"></a>Auto-Modifizierer  
 Die `Auto` -Modifizierer weist die Common Language Runtime, die Zeichenfolge entsprechend dem Methodennamen entsprechend den Regeln der common Language Runtime (oder Aliasnamen, sofern angegeben) konvertieren.  
  
#### <a name="lib-and-alias-keywords"></a>LIB und Alias-Schlüsselwort  
 Folgt den `Function` Schlüsselwort ist der Name Ihrer Anwendung verwendet, um die importierte Funktion zugreifen. Sie können den Namen der aufgerufenen Funktion identisch sein oder können Sie eine beliebige gültige Prozedurnamen und dann einsetzen der `Alias` -Schlüsselwort verwenden, um den tatsächlichen Namen der Funktion angeben, werden.  
  
 Geben Sie die `Lib` -Schlüsselwort, gefolgt vom Namen und Speicherort der DLL mit der Funktion aufrufen. Sie müssen nicht den Pfad zu Dateien in der Windows-Systemverzeichnisse angeben.  
  
 Verwenden der `Alias` Schlüsselwort ist der Name der aufgerufenen Funktion kein gültiger [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Prozedurname oder Konflikte mit dem Namen anderer Elemente in der Anwendung. `Alias`Gibt den eigentlichen Namen der aufgerufenen Funktion an.  
  
#### <a name="argument-and-data-type-declarations"></a>Argument und Deklarationen von Typen  
 Deklarieren Sie die Argumente und deren Datentypen. Dieser Teil kann problematisch sein, da die Datentypen, die Windows mit Visual Studio-Datentypen nicht übereinstimmen. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Führt einen Großteil der Arbeit für Sie durch Konvertieren der Argumente in kompatible Datentypen, eine sogenannte *Marshalling*. Sie können explizit steuern, wie Argumente gemarshallt werden, mithilfe der <xref:System.Runtime.InteropServices.MarshalAsAttribute>Attribut definiert, der <xref:System.Runtime.InteropServices>Namespace.</xref:System.Runtime.InteropServices> </xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
> [!NOTE]
>  Frühere Versionen von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] konnten Sie Parameter deklarieren `As Any`, d. h., Daten eines beliebigen Datentyps verwendet werden konnten. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]erfordert, dass Sie einen bestimmten Datentyp für alle `Declare` Anweisungen.  
  
#### <a name="windows-api-constants"></a>Windows-API-Konstanten  
 Einige Argumente sind Kombinationen von Konstanten. Z. B. die `MessageBox` in dieser exemplarischen Vorgehensweise gezeigten API akzeptiert ein ganzzahliges Argument namens `Typ` , die steuert, wie das Meldungsfeld angezeigt wird. Sie können den numerischen Wert dieser Konstanten bestimmen, indem Sie untersuchen das `#define` Anweisungen in der Datei WinUser.h. Die numerischen Werte werden im Allgemeinen hexadezimal angezeigt, daher sollten Sie mithilfe eines Rechners hinzufügen und Konvertieren in eine Dezimalzahl. Beispielsweise, wenn Sie die Konstanten für das Format mit Ausrufezeichen kombinieren möchten `MB_ICONEXCLAMATION` 0x00000030 und die Ja/kein Format `MB_YESNO` 0 x 00000004, Sie können die Zahlen addieren, und erhalten Sie ein Ergebnis vom, 0 x 00000034 bzw. 52 decimal. Decimal Ergebnis direkt verwenden können, es ist besser, diese Werte als Konstanten in der Anwendung zu deklarieren und kombinieren diese mit der `Or` Operator.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Zum Deklarieren von Konstanten für Windows-API-Aufrufe  
  
1.  Lesen Sie die Dokumentation für die Windows-Funktion, die Sie aufrufen. Bestimmen Sie den Namen der verwendeten Konstanten und den Namen der h-Datei, die die numerischen Werte für diese Konstanten enthält.  
  
2.  Verwenden Sie einen Texteditor wie Editor zum Anzeigen des Inhalts der Headerdatei (. h), und suchen Sie die verwendeten Konstanten zugeordneten Werte. Zum Beispiel die `MessageBox` -API verwendet, die Konstante `MB_ICONQUESTION` zum Anzeigen eines Fragezeichens im Meldungsfeld. Die Definition für `MB_ICONQUESTION` steht in WinUser.h und sieht wie folgt aus:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Fügen Sie die entsprechende `Const` Anweisungen, die der Klasse oder dem Modul diese Konstanten für Ihre Anwendung verfügbar machen. Zum Beispiel:  
  
     [!code-vb[VbVbalrInterop&#11;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>Zum Aufrufen der DLL-Prozedur  
  
1.  Fügen Sie eine Schaltfläche mit dem Namen `Button1` auf den Start des Projekts, und doppelklicken Sie darauf, um ihren Code anzuzeigen. Der Ereignishandler für die Schaltfläche wird angezeigt.  
  
2.  Fügen Sie Code in der `Click` -Ereignishandler für die Schaltfläche, die Sie hinzugefügt haben, rufen Sie die Prozedur, und geben Sie die entsprechenden Argumente:  
  
     [!code-vb[VbVbalrInterop&#12;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Führen Sie das Projekt, indem Sie F5 drücken. Das Meldungsfeld wird angezeigt, mit den beiden **Ja** und **Nr.** Antwort Schaltflächen. Klicken Sie auf eine.  
  
#### <a name="data-marshaling"></a>Marshallen von Daten  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]automatisch konvertiert die Datentypen von Parametern und Rückgabewerten für Windows-API-Aufrufe, aber Sie können die `MarshalAs` Attribut explizit nicht verwaltete Datentypen angeben, die eine API erwartet. Weitere Informationen zum Interop-Marshalling finden Sie unter [Interop-Marshalling](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Deklarieren und mit MarshalAs einen API-Aufruf  
  
1.  Bestimmen Sie den Namen der Funktion sowie deren Argumente, Datentypen, soll und Rückgabewerte.  
  
2.  Um Zugriff auf die `MarshalAs` -Attribut, fügen Sie eine `Imports` -Anweisung am Anfang des Codes für die Klasse oder das Modul wie im folgenden Beispiel:  
  
     [!code-vb[VbVbalrInterop&#13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Fügen Sie einen Funktionsprototyp für die importierte Funktion auf die Klasse oder das Modul, die Sie verwenden und Anwenden der `MarshalAs` -Attribut auf die Parameter oder Rückgabewert. Im folgenden Beispiel ein API-Aufruf, der den Typ erwartet `void*` als gemarshallt `AsAny`:  
  
     [!code-vb[VbVbalrInterop&14;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>API-Aufrufe mit DllImport  
 Das `DllImport` -Attribut bietet eine zweite Möglichkeit, Funktionen in DLLs ohne Typbibliotheken aufzurufen. `DllImport`entspricht ungefähr mit einer `Declare` -Anweisung bietet jedoch besser steuern, wie Funktionen aufgerufen werden.  
  
 Sie können `DllImport` mit den meisten Windows-API aufruft, solange der Aufruf einer freigegebenen gilt (bezeichnet *statische*) Methode. Sie können keine Methoden verwenden, die eine Instanz einer Klasse erforderlich. Im Gegensatz zu `Declare` -Anweisungen, `DllImport` können keine Aufrufe der `MarshalAs` Attribut.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Aufrufen einer Windows-API mit dem DllImport-Attribut  
  
1.  Öffnen Sie ein neues Windows-Anwendungsprojekt, indem Sie auf **neu** auf der **Datei** Menü und dann auf **Projekt**. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Wählen Sie **Windows-Anwendung** aus der Liste der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Projektvorlagen. Das neue Projekt wird angezeigt.  
  
3.  Fügen Sie eine Schaltfläche mit dem Namen `Button2` auf das Startformular.  
  
4.  Doppelklicken Sie auf `Button2` um die Codeansicht für das Formular zu öffnen.  
  
5.  Um Zugriff auf `DllImport`, fügen eine `Imports` -Anweisung am Anfang des Codes für die Startklasse für das Formular:  
  
     [!code-vb[VbVbalrInterop&#13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Deklarieren Sie eine leere Funktion vorhergehenden der `End Class` -Anweisung für das Formular, und der Name der Funktion `MoveFile`.  
  
7.  Anwenden der `Public` und `Shared` Modifizierer für die Deklaration und Festlegen von Parametern für `MoveFile` basierend auf den Argumenten, die die Windows-API-Funktion verwendet:  
  
     [!code-vb[VbVbalrInterop Nr.&16;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     Die Funktion kann ein beliebiger gültiger Prozedurname haben; das `DllImport` -Attribut gibt den Namen in der DLL. Es behandelt auch die Interop-Marshalling für die Parameter und Rückgabewerte, so dass Sie Visual Studio-Datentypen auswählen können, die mit den von der API verwendeten Datentypen.  
  
8.  Anwenden der `DllImport` -Attribut auf die leere Funktion. Der erste Parameter ist der Name und Speicherort der DLL mit der Funktion, die Sie aufrufen. Sie müssen nicht den Pfad zu Dateien in der Windows-Systemverzeichnisse angeben. Der zweite Parameter ist ein benanntes Argument, das den Namen der Funktion in der Windows-API angibt. In diesem Beispiel die `DllImport` -Attribut erzwingt Aufrufe `MoveFile` an `MoveFileW` in KERNEL32. DLL. Die `MoveFileW` -Methode kopiert eine Datei aus dem Pfad `src` zum Pfad `dst`.  
  
     [!code-vb[VbVbalrInterop&17;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Fügen Sie Code in der `Button2_Click` -Ereignishandler, um die Funktion aufzurufen:  
  
     [!code-vb[VbVbalrInterop&18;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Erstellen Sie eine Datei mit dem Namen "Test.txt", und fügen Sie ihn in das Verzeichnis C:\Tmp auf Ihrer Festplatte. Erstellen Sie bei Bedarf die Tmp-Verzeichnis.  
  
11. Drücken Sie F5, um die Anwendung zu starten. Das Hauptformular wird angezeigt.  
  
12. Klicken Sie auf **Button2**. Die Meldung "die Datei wurde erfolgreich verschoben" wird angezeigt, wenn die Datei verschoben werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute>   
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)   
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Erstellen von Prototypen in verwaltetem Code](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d)   
 [Marshalling von Delegaten als Rückrufmethode](http://msdn.microsoft.com/library/6ddd7866-9804-4571-84de-83f5cc017a5a)
