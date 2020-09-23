---
title: 'Exemplarische Vorgehensweise: Aufrufen von Windows-APIs'
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
ms.openlocfilehash: 88b3df2f18add6641d0355d2c605bc5f74dabbc7
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098319"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Exemplarische Vorgehensweise: Aufrufen von Windows-APIs (Visual Basic)

Windows-APIs sind Dynamic Link Libraries (DLLs), die Teil des Windows-Betriebssystems sind. Sie verwenden Sie zum Ausführen von Aufgaben, wenn es schwierig ist, gleichwertige, eigene Prozeduren zu schreiben. Windows stellt z. b. eine Funktion mit dem Namen zur Verfügung `FlashWindowEx` , mit der Sie die Titelleiste für eine Anwendung zwischen hellen und dunklen Schattierungen wechseln können.  
  
 Der Vorteil der Verwendung von Windows-APIs in Ihrem Code besteht darin, dass Sie Entwicklungszeit sparen können, da Sie Dutzende nützlicher Funktionen enthalten, die bereits geschrieben sind und darauf warten, verwendet zu werden. Der Nachteil ist, dass die Arbeit mit Windows-APIs schwierig sein kann und nicht, wenn etwas schief geht.  
  
 Windows-APIs stellen eine spezielle Kategorie von Interoperabilität dar. Windows-APIs verwenden keinen verwalteten Code, verfügen nicht über integrierte Typbibliotheken und verwenden Datentypen, die sich von denen in Visual Studio unterscheiden. Aufgrund dieser Unterschiede und da es sich bei Windows-APIs nicht um COM-Objekte handelt, wird die Interoperabilität mit Windows-APIs und der .NET Framework mithilfe von Platt Form aufrufen oder PInvoke ausgeführt. Der Platt Form Aufruf ist ein Dienst, der verwalteten Code ermöglicht, nicht verwaltete Funktionen aufzurufen, die in DLLs implementiert werden. Weitere Informationen finden Sie unter verwenden [nicht verwalteter DLL-Funktionen](../../../framework/interop/consuming-unmanaged-dll-functions.md). Sie können PInvoke in Visual Basic verwenden, indem Sie entweder die- `Declare` Anweisung verwenden oder das- `DllImport` Attribut auf eine leere Prozedur anwenden.  
  
 Windows-API-Aufrufe waren in der Vergangenheit ein wichtiger Bestandteil der Visual Basic Programmierung, sind jedoch nur selten mit Visual Basic .net erforderlich. Wenn möglich, sollten Sie anstelle von Windows-API-aufrufen verwalteten Code aus dem .NET Framework zum Ausführen von Aufgaben verwenden. Diese exemplarische Vorgehensweise enthält Informationen zu Situationen, in denen die Verwendung von Windows-APIs erforderlich ist.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>API-Aufrufe mithilfe von DECLARE  

 Die gängigste Methode zum Abrufen von Windows-APIs ist die Verwendung der- `Declare` Anweisung.  
  
### <a name="to-declare-a-dll-procedure"></a>So deklarieren Sie eine DLL-Prozedur  
  
1. Bestimmen Sie den Namen der Funktion, die Sie aufzurufen möchten, sowie die Argumente, Argument Typen und den Rückgabewert sowie den Namen und Speicherort der dll, die Sie enthält.  
  
    > [!NOTE]
    > Umfassende Informationen zu den Windows-APIs finden Sie in der Win32 SDK-Dokumentation in der Platform SDK-Windows-API. Weitere Informationen zu den Konstanten, die von Windows-APIs verwendet werden, finden Sie in den Header Dateien wie Windows. h, die im Platform SDK enthalten sind.  
  
2. Öffnen Sie ein neues Windows-Anwendungsprojekt, indem Sie im Menü **Datei** auf **neu** und dann auf **Projekt**klicken. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3. Wählen Sie in der Liste der Visual Basic Projektvorlagen die Option **Windows-Anwendung** aus. Das neue Projekt wird angezeigt.  
  
4. Fügen Sie die folgende `Declare` Funktion entweder der Klasse oder dem Modul hinzu, in der Sie die DLL verwenden möchten:  
  
     [!code-vb[VbVbalrInterop#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#9)]  
  
### <a name="parts-of-the-declare-statement"></a>Teile der Declare-Anweisung  

 Die- `Declare` Anweisung enthält die folgenden Elemente:  
  
#### <a name="auto-modifier"></a>Automatischer Modifizierer  

 Der- `Auto` Modifizierer weist die Runtime an, die Zeichenfolge basierend auf dem Methodennamen gemäß Common Language Runtime Regeln (oder bei Angabe des Alias Namens) zu konvertieren.  
  
#### <a name="lib-and-alias-keywords"></a>Lib-und Alias Schlüsselwörter  

 Der Name, der dem `Function` Schlüsselwort folgt, ist der Name, den das Programm für den Zugriff auf die importierte Funktion verwendet Sie kann mit dem tatsächlichen Namen der Funktion identisch sein, die Sie aufrufen, oder Sie können einen beliebigen gültigen Prozedur Namen verwenden und dann das- `Alias` Schlüsselwort verwenden, um den tatsächlichen Namen der Funktion anzugeben, die Sie aufrufen.  
  
 Geben `Lib` Sie das Schlüsselwort an, gefolgt vom Namen und Speicherort der dll, die die Funktion enthält, die Sie aufrufen. Sie müssen den Pfad für Dateien, die sich in den Windows-Systemverzeichnissen befinden, nicht angeben.  
  
 Verwenden Sie das- `Alias` Schlüsselwort, wenn der Name der Funktion, die Sie aufrufen, kein gültiger Visual Basic Prozedur Name ist oder einen Konflikt mit dem Namen anderer Elemente in der Anwendung verursacht. `Alias` Gibt den tatsächlichen Namen der aufgerufenen Funktion an.  
  
#### <a name="argument-and-data-type-declarations"></a>Argument-und Datentyp Deklarationen  

 Deklarieren Sie die Argumente und deren Datentypen. Dieser Teil kann schwierig sein, da die von Windows verwendeten Datentypen nicht den Visual Studio-Datentypen entsprechen. Visual Basic führt einen großen Teil der Arbeit durch, indem Argumente in kompatible Datentypen, *einen als Marshalling bezeichneten Prozess*, umgerechnet werden. Mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute> im-Namespace definierten-Attributs können Sie explizit steuern, wie Argumente gemarshallt werden <xref:System.Runtime.InteropServices> .  
  
> [!NOTE]
> In früheren Versionen von Visual Basic das Deklarieren von Parametern gestattet `As Any` , was bedeutet, dass Daten eines beliebigen Datentyps verwendet werden können. Visual Basic erfordert, dass Sie einen bestimmten Datentyp für alle- `Declare` Anweisungen verwenden.  
  
#### <a name="windows-api-constants"></a>Windows-API-Konstanten  

 Einige Argumente sind Kombinationen aus Konstanten. Die in dieser exemplarischen Vorgehensweise `MessageBox` gezeigte API akzeptiert beispielsweise ein ganzzahliges Argument mit dem Namen `Typ` , das steuert, wie das Meldungs Feld angezeigt wird. Sie können den numerischen Wert dieser Konstanten ermitteln, indem Sie die `#define` Anweisungen in der Datei "Winuser. h" untersuchen. Die numerischen Werte werden in der Regel im Hexadezimal Format angezeigt. Sie können daher einen Rechner verwenden, um Sie hinzuzufügen und in Decimal zu konvertieren. Wenn Sie z. b. die Konstanten für den Ausrufezeichen Stil `MB_ICONEXCLAMATION` 0x00000030 und den Yes/No-Stil `MB_YESNO` 0x00000004 kombinieren möchten, können Sie die Zahlen hinzufügen und das Ergebnis 0x00000034 oder 52 Decimal erhalten. Obwohl Sie das Dezimal Ergebnis direkt verwenden können, ist es besser, diese Werte als Konstanten in Ihrer Anwendung zu deklarieren und diese mit dem-Operator zu kombinieren `Or` .  
  
##### <a name="to-declare-constants-for-windows-api-calls"></a>So deklarieren Sie Konstanten für Windows-API-Aufrufe  
  
1. Weitere Informationen finden Sie in der Dokumentation der Windows-Funktion, die Sie aufrufen. Bestimmen Sie den Namen der verwendeten Konstanten und den Namen der h-Datei, die die numerischen Werte für diese Konstanten enthält.  
  
2. Verwenden Sie einen Text-Editor, z. b. Notepad, um den Inhalt der Header Datei (. h) anzuzeigen und die Werte zu suchen, die den von Ihnen verwendeten Konstanten zugeordnet sind. Beispielsweise verwendet die `MessageBox` API die Konstante `MB_ICONQUESTION` , um ein Fragezeichen im Meldungs Feld anzuzeigen. Die Definition für `MB_ICONQUESTION` ist in winuser. h und sieht wie folgt aus:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3. Fügen Sie `Const` der Klasse oder dem Modul äquivalente-Anweisungen hinzu, um diese Konstanten für Ihre Anwendung verfügbar zu machen. Beispiel:  
  
     [!code-vb[VbVbalrInterop#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#11)]  
  
###### <a name="to-call-the-dll-procedure"></a>So wenden Sie die DLL-Prozedur an  
  
1. Fügen Sie `Button1` dem Start Formular für das Projekt eine Schaltfläche mit dem Namen hinzu, und doppelklicken Sie darauf, um den Code anzuzeigen. Der Ereignishandler für die Schaltfläche wird angezeigt.  
  
2. Fügen Sie dem- `Click` Ereignishandler Code für die hinzugefügte Schaltfläche hinzu, um die Prozedur aufzurufen und die entsprechenden Argumente bereitzustellen:  
  
     [!code-vb[VbVbalrInterop#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#12)]  
  
3. Führen Sie das Projekt aus, indem Sie F5 drücken. Das Meldungs Feld wird mit den Schaltflächen **Ja** und **keine** Antwort angezeigt. Klicken Sie auf beides.  
  
#### <a name="data-marshaling"></a>Datenmarshalling  

 Visual Basic werden die Datentypen von Parametern und Rückgabe Werten automatisch für Windows-API-Aufrufe konvertiert. Sie können jedoch das-Attribut verwenden, `MarshalAs` um explizit nicht verwaltete Datentypen anzugeben, die von einer API erwartet werden. Weitere Informationen zum Interop-Marshalling finden Sie unter [Interop-Mars](../../../framework/interop/interop-marshaling.md)Hallen.  
  
##### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>So verwenden Sie Declare und MarshalAs in einem API-Befehl  
  
1. Bestimmen Sie den Namen der Funktion, die Sie aufzurufen möchten, sowie die Argumente, Datentypen und den Rückgabewert.  
  
2. Fügen Sie zum Vereinfachen des Zugriffs auf das- `MarshalAs` Attribut eine- `Imports` Anweisung am Anfang des Codes für die Klasse oder das Modul hinzu, wie im folgenden Beispiel gezeigt:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
3. Fügen Sie der von Ihnen verwendeten Klasse oder dem verwendeten Modul einen Funktionsprototyp für die importierte Funktion hinzu, und wenden Sie das- `MarshalAs` Attribut auf die Parameter oder den Rückgabewert an. Im folgenden Beispiel wird ein API-Befehl, der den-Typ erwartet, `void*` wie folgt gemarshallt `AsAny` :  
  
     [!code-vb[VbVbalrInterop#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#14)]  
  
## <a name="api-calls-using-dllimport"></a>API-Aufrufe mithilfe von DllImport  

 Das- `DllImport` Attribut bietet eine zweite Möglichkeit, Funktionen in DLLs ohne Typbibliotheken aufzurufen. `DllImport` entspricht ungefähr der Verwendung einer- `Declare` Anweisung, bietet jedoch mehr Kontrolle über die Art und Weise, wie Funktionen aufgerufen werden.  
  
 Sie können `DllImport` mit den meisten Windows-API-aufrufen verwenden, solange der Aufruf auf eine freigegebene Methode (manchmal als *statisch*bezeichnet) verweist. Sie können keine Methoden verwenden, die eine Instanz einer Klasse erfordern. Im Gegensatz zu- `Declare` Anweisungen `DllImport` können Aufrufe das-Attribut nicht verwenden `MarshalAs` .  
  
### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>So wenden Sie eine Windows-API mit dem DllImport-Attribut an  
  
1. Öffnen Sie ein neues Windows-Anwendungsprojekt, indem Sie im Menü **Datei** auf **neu** und dann auf **Projekt**klicken. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2. Wählen Sie in der Liste der Visual Basic Projektvorlagen die Option **Windows-Anwendung** aus. Das neue Projekt wird angezeigt.  
  
3. Fügen Sie `Button2` dem Start Formular eine Schaltfläche mit dem Namen hinzu.  
  
4. Doppelklicken Sie `Button2` , um die Code Ansicht für das Formular zu öffnen.  
  
5. Fügen Sie zum Vereinfachen des Zugriffs auf `DllImport` eine- `Imports` Anweisung am Anfang des Codes für die Startup-Formular Klasse ein:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
6. Deklarieren Sie eine leere Funktion `End Class` vor der-Anweisung für das Formular, und benennen Sie die Funktion `MoveFile` .  
  
7. Wenden `Public` Sie die `Shared` Modifizierer und auf die Funktionsdeklaration an, und legen Sie Parameter für `MoveFile` basierend auf den Argumenten fest, die die Windows-API-Funktion  
  
     [!code-vb[VbVbalrInterop#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#16)]  
  
     Die Funktion kann einen beliebigen gültigen Prozedur Namen aufweisen. Das- `DllImport` Attribut gibt den Namen in der dll an. Außerdem wird das Interoperabilitäts Marshalling für die Parameter und Rückgabewerte behandelt, sodass Sie Visual Studio-Datentypen auswählen können, die den von der API verwendeten Datentypen ähneln.  
  
8. Wenden Sie das- `DllImport` Attribut auf die leere Funktion an. Der erste Parameter ist der Name und Speicherort der dll, die die Funktion enthält, die Sie aufrufen. Sie müssen den Pfad für Dateien, die sich in den Windows-Systemverzeichnissen befinden, nicht angeben. Der zweite Parameter ist ein benanntes Argument, das den Namen der Funktion in der Windows-API angibt. In diesem Beispiel `DllImport` erzwingt das-Attribut, `MoveFile` dass Aufrufe von in KERNEL32.DLL weitergeleitet werden `MoveFileW` . Mit der- `MoveFileW` Methode wird eine Datei aus dem Pfad `src` in den Pfad kopiert `dst` .  
  
     [!code-vb[VbVbalrInterop#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#17)]  
  
9. Fügen Sie dem- `Button2_Click` Ereignishandler Code hinzu, um die-Funktion aufzurufen:  
  
     [!code-vb[VbVbalrInterop#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#18)]  
  
10. Erstellen Sie eine Datei mit dem Namen Test.txt, und platzieren Sie Sie im Verzeichnis c:\tmp auf der Festplatte. Erstellen Sie ggf. das tmp-Verzeichnis.  
  
11. Drücken Sie F5, um die Anwendung zu starten. Das Hauptformular wird angezeigt.  
  
12. Klicken Sie auf **Button2**. Die Meldung "die Datei wurde erfolgreich verschoben" wird angezeigt, wenn die Datei verschoben werden kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Declare Statement](../../language-reference/statements/declare-statement.md)
- [Auto](../../language-reference/modifiers/auto.md)
- [Alias](../../language-reference/statements/alias-clause.md)
- [COM-Interop](index.md)
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [Marshalling von Delegaten als Rückrufmethode](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
