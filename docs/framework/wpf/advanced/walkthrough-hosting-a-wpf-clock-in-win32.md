---
title: 'Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caf652f8a80da8e927a74ffc012d09b2389b1b09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32
Versetzen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] -Anwendungen verwenden <xref:System.Windows.Interop.HwndSource>, stellt das HWND, die enthält Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt. Erstellen Sie zuerst die <xref:System.Windows.Interop.HwndSource>, und geben sie Ihnen Parameter CreateWindow ähnelt.  Setzen Sie die <xref:System.Windows.Interop.HwndSource> über die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Content soll darin.  Schließlich erhalten Sie das HWND aus der <xref:System.Windows.Interop.HwndSource>. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie ein gemischtes erstellen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Anwendung, die das Betriebssystemdialogfeld **Datums- und Uhrzeiteigenschaften** Dialogfeld.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Finden Sie unter [WPF und Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## <a name="how-to-use-this-tutorial"></a>Verwendung dieses Tutorials  
 Dieses Tutorial konzentriert sich auf die wichtigsten Schritte zum Erstellen einer interoperativen Anwendung. Ein Beispiel des Lernprogramms gesichert ist [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051), aber dieser Beispiel wird das Endprodukt reflektiert. In diesem Lernprogramm werden die Schritte aus, als ob Sie mit einem vorhandenen gestartet wurden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt Ihrer Wahl und möglicherweise einem vorhandenen Projekt eine gehostete hinzufügen wurden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für Ihre Anwendung. Sie können Ihre Endprodukt mit vergleichen [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Eine exemplarische Vorgehensweise für Windows Presentation Framework in Win32 (HwndSource)  
 Die folgende Grafik zeigt das angestrebte Endprodukt dieses Tutorials:  
  
 ![Dialogfeld Datums- und Uhrzeiteigenschaften](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")  
  
 Sie können dieses Dialogfeld erstellen, durch das Erstellen von C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], und verwenden den Dialog-Editor Folgendes erstellen:  
  
 ![Dialogfeld Datums- und Uhrzeiteigenschaften](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")  
  
 (Sie müssen nicht verwenden [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] verwenden <xref:System.Windows.Interop.HwndSource>, und Sie müssen nicht mit C++ schreiben [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Programme, aber dies eine Recht typische Möglichkeit dafür ist, und eignet sich gut für eine schrittweise Erklärung der Tutorial).  
  
 Müssen Sie fünf bestimmte Schritte zu erreichen, um das Einfügen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr in das Dialogfeld ":  
  
1.  Aktivieren der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt verwalteten Code aufrufen (**"/ CLR"**) durch Ändern von projekteinstellungen in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
2.  Erstellen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> in einer separaten DLL.  
  
3.  Einfügen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> innerhalb einer <xref:System.Windows.Interop.HwndSource>.  
  
4.  Rufen Sie ein HWND für diese <xref:System.Windows.Controls.Page> mithilfe der <xref:System.Windows.Interop.HwndSource.Handle%2A> Eigenschaft.  
  
5.  Verwendung [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] entscheiden, platzieren Sie das HWND in der größeren [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Anwendung  
  
## <a name="clr"></a>/clr  
 Der erste Schritt ist das nicht verwaltete aktivieren [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] von verwaltetem Code Projekt in eine, die aufgerufen werden können.  Verwenden Sie die Compileroption "/ CLR", die mit den erforderlichen DLLs Sie verwenden möchten verknüpft werden, und passen Sie die Main-Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 So aktivieren Sie die Verwendung von verwaltetem Code im C++-Projekt: mit der rechten Maustaste auf win32clock-Projekt, und wählen Sie **Eigenschaften**.  Auf der **allgemeine** Eigenschaftenseite "" (Standard), ändern Sie Common Language Runtime-Unterstützung in `/clr`.  
  
 Als Nächstes fügen Sie Verweise auf DLLs, die für die erforderlichen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll "System.dll", WindowsBase.dll, UIAutomationProvider.dll und UIAutomationTypes.dll. (Bei den nachfolgenden Anweisungen wird davon ausgegangen, dass das Betriebssystem auf Laufwerk C: installiert ist.)  
  
1.  Mit der rechten Maustaste win32clock-Projekt, und wählen Sie **Verweise...** , und klicken Sie in diesem Dialogfeld:  
  
2.  Mit der rechten Maustaste win32clock-Projekt, und wählen Sie **Verweise...** .  
  
3.  Klicken Sie auf **neuen Verweis hinzufügen**, klicken Sie auf die Registerkarte "Durchsuchen", geben Sie c:\Programme\Microsoft c:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, und klicken Sie auf OK.  
  
4.  Wiederholen Sie diesen Schritt für PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.  
  
5.  Wiederholen Sie diesen Schritt für WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.  
  
6.  Wiederholen Sie diesen Schritt für UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.  
  
7.  Wiederholen Sie diesen Schritt für UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.  
  
8.  Klicken Sie auf **neuen Verweis hinzufügen**, wählen Sie "System.dll" aus, und klicken Sie auf **OK**.  
  
9. Klicken Sie auf **OK** um die win32clock-Eigenschaftenseiten für das Hinzufügen von Verweisen zu beenden.  
  
 Fügen Sie schließlich die `STAThreadAttribute` auf die `_tWinMain` Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 Dieses Attribut weist die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] , wenn es initialisiert [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], sollten Sie ein Modell Singlethread-Apartment (STA), die für erforderlich ist verwenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).  
  
## <a name="create-a-windows-presentation-framework-page"></a>Erstellen einer Windows Presentation Framework-Seite  
 Als Nächstes erstellen Sie eine DLL, definiert einen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>. Häufig ist es am einfachsten, erstellen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> als eigenständige Anwendung, und Schreiben und Debuggen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil auf diese Weise.  Sobald erfolgt, kann dieses Projekt in eine DLL aktiviert werden, mit der rechten Maustaste auf das Projekt **Eigenschaften**, navigieren Sie zu der Anwendung und Ausgabetyp in Windows-Klassenbibliothek ändern.  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Dll-Projekt kann dann zusammen mit den [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt (eine Lösung, die zwei Projekte enthält) – mit der rechten Maustaste auf die Projektmappe, wählen **vorhandenes Projekt**.  
  
 Verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Dll aus dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] -Projekt müssen Sie einen Verweis hinzu:  
  
1.  Mit der rechten Maustaste win32clock-Projekt, und wählen Sie **Verweise...** .  
  
2.  Klicken Sie auf **neuen Verweis hinzufügen**.  
  
3.  Klicken Sie auf die Registerkarte **Projekte**.  Wählen Sie „WPFClock” aus und klicken Sie auf OK.  
  
4.  Klicken Sie auf **OK** um die win32clock-Eigenschaftenseiten für das Hinzufügen von Verweisen zu beenden.  
  
## <a name="hwndsource"></a>HwndSource  
 Verwenden Sie als Nächstes <xref:System.Windows.Interop.HwndSource> vornehmen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> HWND aussehen.  Sie fügen diesen Codeblock zu einer C++-Datei hinzu:  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
  
    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
        HwndSource^ source = gcnew HwndSource(  
            0, // class style  
            WS_VISIBLE | WS_CHILD, // style  
            0, // exstyle  
            x, y, width, height,  
            "hi", // NAME  
            IntPtr(parent)        // parent window   
            );  
  
        UIElement^ page = gcnew WPFClock::Clock();  
        source->RootVisual = page;  
        return (HWND) source->Handle.ToPointer();  
    }  
}  
}  
```  
  
 Dies ist ein langer Codeabschnitt, der einiger Erklärungen bedarf.  Der erste Teil besteht aus verschiedenen Klauseln, die dafür sorgen, dass nicht alle Aufrufe vollständig qualifiziert werden müssen:  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 Anschließend definieren Sie eine Funktion, die erstellt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt, setzt eine <xref:System.Windows.Interop.HwndSource> um, und gibt den HWND zurück:  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 Zunächst erstellen Sie eine <xref:System.Windows.Interop.HwndSource>, deren Parameter CreateWindow ähneln:  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 Anschließend Sie erstellen die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content-Klasse durch Aufrufen des Konstruktors:  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 Verbinden Sie Sie dann die Seite die <xref:System.Windows.Interop.HwndSource>:  
  
```  
source->RootVisual = page;  
```  
  
 Und in die letzte Zeile zurückzugeben HWND für die <xref:System.Windows.Interop.HwndSource>:  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a>Positionieren des HWND  
 Nun, dass Sie einen HWND haben, enthält die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr, müssen Sie das HWND platziert die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Dialogfeld.  Wenn Sie nur eines Speicherorts für das HWND wussten, würde übergeben Sie einfach, die Größe und Position, an die `GetHwnd` zuvor definierte Funktion.  Da Sie für die Definition des Dialogs aber eine Ressourcendatei verwendet haben, können Sie nicht sicher wissen, wo ein HWND jeweils platziert sein wird.  Können Sie die [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] Dialog-Editor, eingefügt werden soll eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] statische steuern die Uhr wechseln soll ("Uhr hier einfügen"), und verwenden Sie diese zum Positionieren der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr.  
  
 Bei WM_INITDIALOG können Sie verwenden, `GetDlgItem` das HWND für den STATIC-Platzhalter abrufen:  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 Sie klicken Sie dann berechnen die Größe und Position des Platzhalters STATIC "," damit Sie platzieren können die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock an dieser Stelle:  
  
 RECT rectangle;  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 Blenden Sie anschließen den Platzhalter „STATIC” aus:  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 Und erstellen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND an diesem Speicherort:  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 Lernprogramm interessanter und um eine echte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr, müssen Sie erstellen eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement zu diesem Zeitpunkt clock. Den größten Teil davon können Sie in Markup erledigen, mit nur einigen wenigen Ereignishandlern im CodeBehind. Da dieses Lernprogramm auf Informationen über die Interoperation und nicht zum Entwerfen von Steuerelement wird, wird der vollständige Code für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr erfolgt hier als ein Codeblock, ohne separate Anweisungen zum Aufbau und der Bedeutung der einzelnen Teile. Experimentieren Sie ruhig mit diesem Code, um Aussehen, Verhalten oder Funktionalität des Steuerelements zu ändern.  
  
 Dies ist das Markup:  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 Und hier das zugehörige CodeBehind:  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 Das Endergebnis sieht folgendermaßen aus:  
  
 ![Dialogfeld Datums- und Uhrzeiteigenschaften](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")  
  
 Um Ihr Ergebnis an den Code zu vergleichen, die diesem Screenshot erzeugt, finden Sie unter [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Interop.HwndSource>  
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Beispiel für Interaktion mit der Win32-Uhr](http://go.microsoft.com/fwlink/?LinkID=160051)
