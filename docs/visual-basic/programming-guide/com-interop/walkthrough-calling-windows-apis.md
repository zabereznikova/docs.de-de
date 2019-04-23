---
title: 'Exemplarische Vorgehensweise: Aufrufen von Windows-APIs (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
ms.openlocfilehash: 8fd63c2abedcd416937e2c281486bdc1716a275f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332325"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Exemplarische Vorgehensweise: Aufrufen von Windows-APIs (Visual Basic)
Windows-APIs sind Dynamic Link Libraries (DLLs), die Teil des Windows-Betriebssystems sind. Können Sie diese Aufgaben auszuführen, wenn es schwierig, Ihre eigenen Prozeduren zu schreiben ist. Windows stellt z. B. eine Funktion namens `FlashWindowEx` , mit der Sie die Titelleiste für eine Anwendung wechseln Sie zwischen hellen und dunklen Graustufen.  
  
 Der Vorteil der Verwendung von Windows-APIs in Ihrem Code ist, dass sie Entwicklungszeit einsparen können, da sie enthalten, Dutzende von nützlichen Funktionen, die bereits geschrieben wurden und darauf warten, verwendet werden. Der Nachteil ist, dass die Windows-APIs arbeiten mit und fehleranfällig, wenn etwas schief geht, schwierig sein kann.  
  
 Windows-APIs stellen eine besondere Kategorie der Interoperabilität dar. Windows-APIs verwenden nicht verwalteten Code, verfügen nicht über integrierte Typbibliotheken, und verwenden die Datentypen unterscheiden, die mit Visual Studio verwendet. Aufgrund dieser Unterschiede und da Windows-APIs nicht COM-Objekten, die Interoperabilität mit Windows-APIs sind und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] erfolgt unter Verwendung der Plattform aufrufen, oder PInvoke. Der Plattformaufruf ist ein Dienst, der von verwaltetem Code zum Aufrufen von nicht verwalteter Funktionen in DLLs implementiert werden können. Weitere Informationen finden Sie unter [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md). Sie können die PInvoke in Visual Basic verwenden, indem Sie entweder die `Declare` -Anweisung oder das Anwenden der `DllImport` -Attribut auf eine leere Prozedur.  
  
 Windows-API-Aufrufe ein wichtiger Teil der Visual Basic-Programmierung in der Vergangenheit wurden, sind aber selten notwendig, mit Visual Basic .NET. Wann immer möglich, sollten Sie verwalteten Code von verwenden die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] zum Ausführen von Aufgaben anstelle von Windows-API-Aufrufe. Diese exemplarische Vorgehensweise enthält Informationen über die Situationen, in denen die Verwendung Windows-APIs erforderlich ist.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Deklarieren von API-Aufrufe mit  
 Die gängigste Methode zum Aufrufen von Windows-APIs ist die Verwendung der `Declare` Anweisung.  
  
#### <a name="to-declare-a-dll-procedure"></a>Deklarieren eine DLL-Prozedur  
  
1. Bestimmen Sie den Namen der Funktion, die Sie aufrufen möchten, sowie die Argumente, die Argumenttypen und zurück-Wert, als auch den Namen und Speicherort der DLL, die sie enthält.  
  
    > [!NOTE]
    >  Ausführliche Informationen zu den Windows-APIs finden Sie unter den Win32 SDK-Dokumentation in der Platform SDK-Windows-API. Weitere Informationen über die Konstanten, die Windows-APIs verwenden, überprüfen Sie die Headerdateien, z. B. Windows.h in im Plattform-SDK enthalten.  
  
2. Öffnen Sie ein neues Windows-Anwendungsprojekt, indem Sie auf **neu** auf die **Datei** Menü, und klicken Sie dann auf **Projekt**. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3. Wählen Sie **Windows-Anwendung** aus der Liste der Projektvorlagen für Visual Basic. Das neue Projekt wird angezeigt.  
  
4. Fügen Sie die folgenden `Declare` Funktion entweder auf die Klasse oder das Modul, in dem Sie die DLL verwenden möchten:  
  
     [!code-vb[VbVbalrInterop#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#9)]  
  
### <a name="parts-of-the-declare-statement"></a>Teile der Declare-Anweisung  
 Die `Declare` Anweisung enthält die folgenden Elemente.  
  
#### <a name="auto-modifier"></a>Auto-Modifizierer  
 Die `Auto` Modifizierer weist die Runtime die Zeichenfolge, die basierend auf den Methodennamen entsprechend den Regeln der common Language Runtime (oder Aliasname angegeben) zu konvertieren.  
  
#### <a name="lib-and-alias-keywords"></a>LIB "und"-Alias-Schlüsselwörter  
 Die folgenden Namen der `Function` -Schlüsselwort ist der Name Ihrer Anwendung verwendet, um den Zugriff auf die importierten Funktion. Kann es sein, identisch mit den tatsächlichen Namen der Funktion, die Sie aufrufen, oder Sie können alle gültigen Prozedurnamen und klicken Sie dann einsetzen der `Alias` Schlüsselwort, um den tatsächlichen Namen der Funktion geben Sie Sie aufrufen.  
  
 Geben Sie die `Lib` Schlüsselwort, gefolgt von den Namen und Speicherort der DLL, die die Funktion enthält Sie aufrufen. Sie müssen sich nicht um den Pfad zu Dateien in der Windows-Systemverzeichnisse anzugeben.  
  
 Verwenden der `Alias` Schlüsselwort, wenn der Name der Funktion, die Sie aufrufen, ist kein Name ein gültiger Visual Basic-Prozedur oder steht in Konflikt mit dem Namen anderer Elemente in Ihrer Anwendung. `Alias` Gibt den tatsächlichen Namen der aufgerufenen Funktion an.  
  
#### <a name="argument-and-data-type-declarations"></a>Argument "und" Data-Type-Deklarationen  
 Deklarieren Sie die Argumente und deren Datentypen. Dieser Teil kann schwierig sein, da die Datentypen, die Windows verwendet Visual Studio-Datentypen nicht übereinstimmen. Visual Basic ist eine Menge Arbeit für Sie durch die Konvertierung von Argumenten zu kompatiblen Datentypen einen Prozess namens *Marshalling*. Sie können explizit steuern, wie Argumente gemarshallt werden, mithilfe der <xref:System.Runtime.InteropServices.MarshalAsAttribute> im definierten Attribut der <xref:System.Runtime.InteropServices> Namespace.  
  
> [!NOTE]
>  Frühere Versionen von Visual Basic konnten Sie Parameter zu deklarieren `As Any`, d. h. diese Daten für alle Daten verwendet werden konnten. Visual Basic erfordert, dass Sie einen bestimmten Datentyp für alle verwenden `Declare` Anweisungen.  
  
#### <a name="windows-api-constants"></a>Windows-API-Konstanten  
 Einige Argumente sind Kombinationen von Konstanten. Z. B. die `MessageBox` in dieser exemplarischen Vorgehensweise gezeigten API akzeptiert ein ganzzahliges Argument aufgerufen `Typ` , die steuert, wie das Meldungsfeld angezeigt wird. Sie können den numerischen Wert dieser Konstanten bestimmen, indem Sie die Untersuchung der `#define` Anweisungen in der WinUser.h-Datei. Die numerischen Werte werden im Hexadezimalformat, in der Regel angezeigt, daher Sie verwenden einen Rechner sollten, um Sie hinzuzufügen, und Konvertieren in eine Dezimalzahl. Wenn Sie die Konstanten für das Ausrufezeichen Format kombinieren möchten z. B. `MB_ICONEXCLAMATION` 0x00000030 und die Ja/keine Formatvorlage `MB_YESNO` 0 x 00000004, Sie können die Zahlen addieren und erhalten ein Ergebnis, 0 x 00000034 bzw. 52 Dezimalformat. Sie können das decimal Ergebnis direkt verwenden, es ist besser, deklarieren diese Werte als Konstanten in der Anwendung und kombinieren mithilfe der `Or` Operator.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Zum Deklarieren von Konstanten für die Windows-API-Aufrufe  
  
1. Lesen Sie die Dokumentation für die Windows-Funktion, die Sie aufrufen. Bestimmen Sie den Namen der verwendeten Konstanten und den Namen der h-Datei, die die numerischen Werte für diese Konstanten enthält.  
  
2. Verwenden Sie einen Text-Editor wie Editor zum Anzeigen des Inhalts der Headerdatei (. h), und suchen Sie die Werte der Konstanten, die Sie verwenden. Z. B. die `MessageBox` -API verwendet die Konstante `MB_ICONQUESTION` zu einem Fragezeichen in der MessageBox anzeigen. Die Definition für `MB_ICONQUESTION` steht in WinUser.h und sieht wie folgt aus:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3. Hinzufügen der entsprechenden `Const` Anweisungen, die der Klasse oder das Modul, um diese Konstanten für Ihre Anwendung verfügbar machen. Zum Beispiel:  
  
     [!code-vb[VbVbalrInterop#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#11)]  
  
###### <a name="to-call-the-dll-procedure"></a>Die DLL-Prozedur aufrufen  
  
1. Fügen Sie eine Schaltfläche mit dem Namen `Button1` auf den Start des Projekts, und doppelklicken Sie darauf, um ihren Code anzuzeigen. Der Ereignishandler für die Schaltfläche wird angezeigt.  
  
2. Fügen Sie Code in die `Click` -Ereignishandler für die Schaltfläche, die Sie hinzugefügt haben, rufen Sie die Prozedur, und geben Sie die entsprechenden Argumenten:  
  
     [!code-vb[VbVbalrInterop#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#12)]  
  
3. Führen Sie das Projekt durch Drücken von F5. Das Meldungsfeld wird angezeigt, mit den beiden **Ja** und **keine** Antwort Schaltflächen. Klicken Sie auf eines.  
  
#### <a name="data-marshaling"></a>Daten-Marshalling  
 Visual Basic konvertiert automatisch die Datentypen der Parameter und Rückgabewerte für die Windows-API-Aufrufe, aber Sie können die `MarshalAs` Attribut explizit nicht verwaltete Datentypen angeben, die eine API erwartet. Weitere Informationen zum Interop-Marshalling, finden Sie unter [Interop-Marshalling](../../../framework/interop/interop-marshaling.md).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Verwenden von Declare und MarshalAs in einer API-Aufruf  
  
1. Bestimmen Sie den Namen der Funktion aufgerufen werden, sowie deren Argumente, Datentypen werden soll, und Wert zurück.  
  
2. Zur Vereinfachung der Zugriff auf die `MarshalAs` -Attribut enthält, fügen eine `Imports` Anweisung am Anfang des Codes für die Klasse oder das Modul, wie im folgenden Beispiel gezeigt:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
3. Fügen Sie einen Funktionsprototyp, für die importierte Funktion auf die Klasse oder das Modul, die Sie verwenden und Anwenden der `MarshalAs` -Attribut auf die Parameter oder Rückgabewert. Im folgenden Beispiel ist ein API-Aufruf, der den Typ erwartet `void*` wird gemarshallt als `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#14)]  
  
## <a name="api-calls-using-dllimport"></a>API-Aufrufe mit DllImport  
 Die `DllImport` Attribut bietet eine zweite Möglichkeit zum Aufrufen von Funktionen in DLLs ohne Typbibliotheken. `DllImport` ist ungefähr äquivalent zur Verwendung einer `Declare` Anweisung bietet jedoch mehr Kontrolle über die wie Funktionen aufgerufen werden.  
  
 Sie können `DllImport` mit den meisten Windows-API aufruft, solange der Aufruf an einen freigegebenen verweist (bezeichnet *statische*) Methode. Sie können keine Methoden, die eine Instanz einer Klasse benötigen. Im Gegensatz zu `Declare` Anweisungen `DllImport` können keine Aufrufe der `MarshalAs` Attribut.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Zum Aufrufen einer Windows-API, die mit dem DllImport-Attribut  
  
1. Öffnen Sie ein neues Windows-Anwendungsprojekt, indem Sie auf **neu** auf die **Datei** Menü, und klicken Sie dann auf **Projekt**. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2. Wählen Sie **Windows-Anwendung** aus der Liste der Projektvorlagen für Visual Basic. Das neue Projekt wird angezeigt.  
  
3. Fügen Sie eine Schaltfläche mit dem Namen `Button2` auf das Startformular.  
  
4. Doppelklicken Sie auf `Button2` die Codeansicht für das Formular zu öffnen.  
  
5. Zur Vereinfachung der Zugriff auf `DllImport`, Hinzufügen einer `Imports` Anweisung am Anfang des Codes für die Startup-Form-Klasse:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
6. Deklarieren Sie eine leere Funktion vorherigen der `End Class` -Anweisung für das Formular, und klicken Sie auf die Namen der Funktion `MoveFile`.  
  
7. Anwenden der `Public` und `Shared` Modifizierer der Deklaration der Funktion und Festlegen von Parametern für `MoveFile` basierend auf den Argumenten, die die Windows-API-Funktion verwendet:  
  
     [!code-vb[VbVbalrInterop#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#16)]  
  
     Die Funktion kann ein beliebiger gültiger Prozedurname haben; die `DllImport` -Attribut gibt den Namen in der DLL. Er führt auch die Interop-Marshalling für die Parameter und Rückgabewerte, sodass Sie Visual Studio-Datentypen auswählen können, die auf die Daten ähneln der API verwendeten Datentypen.  
  
8. Anwenden der `DllImport` Attribut der empty-Funktion. Der erste Parameter ist der Name und Speicherort der DLL mit der Funktion, die Sie aufrufen. Sie müssen sich nicht um den Pfad zu Dateien in der Windows-Systemverzeichnisse anzugeben. Der zweite Parameter ist ein benanntes Argument, das den Namen der Funktion in der Windows-API angibt. In diesem Beispiel die `DllImport` Attribut erzwingt, dass Aufrufe von `MoveFile` an `MoveFileW` in KERNEL32. DLL. Die `MoveFileW` -Methode kopiert eine Datei aus dem Pfad `src` auf den Pfad `dst`.  
  
     [!code-vb[VbVbalrInterop#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#17)]  
  
9. Fügen Sie Code in die `Button2_Click` -Ereignishandler, um die Funktion aufrufen:  
  
     [!code-vb[VbVbalrInterop#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#18)]  
  
10. Erstellen Sie eine Datei mit dem Namen "Test.txt", und fügen Sie ihn in das Verzeichnis "C:\Tmp" auf Ihrer Festplatte. Erstellen Sie ggf. die Tmp-Verzeichnis.  
  
11. Drücken Sie F5, um die Anwendung zu starten. Das Hauptformular angezeigt wird.  
  
12. Klicken Sie auf **Button2**. Die Meldung "die Datei erfolgreich verschoben wurde" wird angezeigt, wenn die Datei verschoben werden kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)
- [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [Marshallen von Delegaten als Rückrufmethode](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
