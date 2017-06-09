---
title: "Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Interoperabilität [WPF], Lernprogramme"
  - "Interoperabilität [WPF], Win32"
  - "Win32-Code, WPF-Interoperation"
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32
Wenn Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalte in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Anwendungen platzieren möchten, verwenden Sie <xref:System.Windows.Interop.HwndSource>. Hierdurch erhalten Sie das HWND für Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt.  Erstellen Sie zunächst die <xref:System.Windows.Interop.HwndSource> mit Parametern, die denen von CreateWindow ähneln.  Informieren Sie dann <xref:System.Windows.Interop.HwndSource> über den aufzunehmenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt.  Abschließend extrahieren Sie das HWND aus <xref:System.Windows.Interop.HwndSource>.  In diesem Beispiel erfahren Sie, wie Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt in einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Anwendung erstellen, die das Betriebssystemdialogfeld **Eigenschaften von Datum und Uhrzeit** erneut implementiert.  
  
## Vorbereitungsmaßnahmen  
 Weitere Informationen finden Sie unter [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## So verwenden Sie dieses Lernprogramm  
 Dieses Lernprogramm konzentriert sich auf die wichtigsten, beim Erstellen einer Interoperationsanwendung erforderlichen Schritte.  Das Lernprogramm wird durch ein Beispiel ergänzt \([Beispiel für die Win32\-Uhrinteroperation](http://go.microsoft.com/fwlink/?LinkID=160051)\), das jedoch unser Endprodukt reflektiert.  Die Schritte in diesem Lernprogramm basieren auf der Annahme, dass Sie mit einem eigenen, bereits vorhandenen [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Projekt arbeiten und Ihrer Anwendung gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt hinzufügen.  Sie können Ihr Endprodukt dann mit dem Beispiel unter [Beispiel für die Win32\-Uhrinteroperation](http://go.microsoft.com/fwlink/?LinkID=160051) vergleichen.  
  
## Beispiel für Windows Presentation Framework\-Inhalte in Win32 \(HwndSource\)  
 Die folgende Grafik zeigt das in diesem Lernprogramm angestrebte Endprodukt:  
  
 ![Dialogfeld Datums&#45; und Uhrzeiteigenschaften](../../../../docs/framework/wpf/advanced/media/interoparch06.png "InteropArch06")  
  
 Sie können dieses Dialogfeld erstellen, indem Sie zunächst ein C\+\+\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Projekt in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] und dann Folgendes mit dem Dialog\-Editor erstellen:  
  
 ![Dialogfeld Datums&#45; und Uhrzeiteigenschaften](../../../../docs/framework/wpf/advanced/media/interoparch07.png "InteropArch07")  
  
 \(Sie können <xref:System.Windows.Interop.HwndSource> auch ohne [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] verwenden und [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Programme auch ohne C\+\+ schreiben, die hier beschriebene Vorgehensweise ist jedoch ein relativ typischer Ansatz und gut für die schrittweise Erläuterung in einem Lernprogramm geeignet.\)  
  
 Es sind fünf spezifische Schritte erforderlich, um eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Uhr in das Dialogfeld einzufügen:  
  
1.  Aktivieren Sie Ihr [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Projekt so, dass verwalteter Code \(**\/clr**\) aufgerufen wird, indem Sie die Projekteinstellungen in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] ändern.  
  
2.  Erstellen Sie in einer separaten DLL ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.Page>\-Element.  
  
3.  Platzieren Sie dieses [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.Page>\-Element in einem <xref:System.Windows.Interop.HwndSource>\-Element.  
  
4.  Rufen Sie mithilfe der <xref:System.Windows.Interop.HwndSource.Handle%2A>\-Eigenschaft ein HWND für diese <xref:System.Windows.Controls.Page> auf.  
  
5.  Verwenden Sie [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], um zu entscheiden, an welcher Stelle in der größeren [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Anwendung das HWND platziert werden soll.  
  
## \/clr  
 Konvertieren Sie zunächst das nicht verwaltete [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Projekt in ein Projekt, das verwalteten Code aufrufen kann.  Verwenden Sie die \/clr\-Compileroption, die eine Verbindung mit den gewünschten erforderlichen DLLs herstellt, und passen Sie die Main\-Methode an die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] an.  
  
 So ermöglichen Sie die Verwendung von verwaltetem Code im C\+\+\-Projekt: Klicken Sie mit der rechten Maustaste auf das win32clock\-Projekt, und wählen Sie die Option **Eigenschaften** aus.  Ändern Sie auf der Eigenschaftenseite **Allgemein** \(Standardseite\) die Common Language Runtime\-Unterstützung in `/clr`.  
  
 Fügen Sie dann Verweise auf die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erforderlichen DLLs hinzu: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll und UIAutomationTypes.dll.  \(Bei den folgenden Anleitungen wird davon ausgegangen, dass das Betriebssystem auf dem Laufwerk C: installiert ist.\)  
  
1.  Klicken Sie mit der rechten Maustaste auf das win32clock\-Projekt, und wählen Sie **Verweise...** aus. In diesem Dialogfeld:  
  
2.  Klicken Sie mit der rechten Maustaste auf das win32clock\-Projekt, und wählen Sie **Verweise...** aus.  
  
3.  Klicken Sie auf **Neuen Verweis hinzufügen**, klicken Sie auf die Registerkarte Durchsuchen, geben Sie C:\\Programme\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\PresentationCore.dll ein, und klicken Sie auf OK.  
  
4.  Wiederholen Sie diese Schritte für die PresentationFramework.dll: C:\\Programme\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\PresentationFramework.dll.  
  
5.  Wiederholen Sie diese Schritte für die WindowsBase.dll: C:\\Programme\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\WindowsBase.dll.  
  
6.  Wiederholen Sie diese Schritte für die UIAutomationTypes.dll: C:\\Programme\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\UIAutomationTypes.dll.  
  
7.  Wiederholen Sie diese Schritte für die UIAutomationProvider.dll: C:\\Programme\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\UIAutomationProvider.dll.  
  
8.  Klicken Sie auf **Neuen Verweis hinzufügen**, wählen Sie die System.dll aus, und klicken Sie auf **OK**.  
  
9. Klicken Sie auf **OK**, um die win32clock\-Eigenschaftenseiten zum Hinzufügen von Verweisen zu schließen.  
  
 Fügen Sie abschließend `STAThreadAttribute` zur `_tWinMain`\-Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hinzu:  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 Dieses Attribut zeigt der [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] an, dass bei der Initialisierung von [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)] ein Singlethread\-Apartment\-Modell \(STA\), das für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(und für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\) benötigt wird, verwendet werden muss.  
  
## Erstellen einer Windows Presentation Framework\-Seite  
 Als Nächstes erstellen Sie eine DLL, die eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.Page> definiert.  Häufig ist es am einfachsten, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.Page> als eigenständige Anwendung zu erstellen und dann auf diese Weise den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-seitigen Teil zu schreiben und zu debuggen.  Abschließend können Sie das Projekt in eine DLL konvertieren, indem Sie mit der rechten Maustaste auf das Projekt klicken, **Eigenschaften** auswählen, zur Anwendung wechseln und den Ausgabetyp in Windows\-Klassenbibliothek ändern.  
  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-DLL\-Projekt kann dann mit dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Projekt kombiniert werden \(eine Projektmappe mit beiden Projekten\): Klicken Sie mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Vorhandenes Projekt hinzufügen** aus.  
  
 Um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-DLL aus dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Projekt zu verwenden, müssen Sie einen Verweis hinzufügen:  
  
1.  Klicken Sie mit der rechten Maustaste auf das win32clock\-Projekt, und wählen Sie **Verweise...** aus.  
  
2.  Klicken Sie auf **Neuen Verweis hinzufügen**.  
  
3.  Klicken Sie auf die Registerkarte **Projekte**.  Wählen Sie die WPF\-Uhr \(WPFClock\) aus, und klicken Sie auf OK.  
  
4.  Klicken Sie auf **OK**, um die win32clock\-Eigenschaftenseiten zum Hinzufügen von Verweisen zu schließen.  
  
## HwndSource  
 Jetzt verwenden Sie das <xref:System.Windows.Interop.HwndSource-Element>, um das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.Page>\-Element wie ein HWND aussehen zu lassen.  Fügen Sie den folgenden Codeblock zu einer C\+\+\-Datei hinzu:  
  
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
  
 Dieser große Codeabschnitt bedarf wohl noch einiger Erklärungen.  Beim ersten Teil handelt es sich um verschiedene Klauseln, damit nicht alle Aufrufe vollständig qualifiziert werden müssen:  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 Anschließend definieren Sie eine Funktion, die den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt erstellt und in <xref:System.Windows.Interop.HwndSource> platziert und das HWND zurückgibt:  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 Erstellen Sie zuerst eine <xref:System.Windows.Interop.HwndSource> mit Parametern, die denen von CreateWindow ähneln:  
  
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
  
 Dann erstellen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltsklasse, indem Sie ihren Konstruktor aufrufen:  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 Jetzt wird die Seite mit der <xref:System.Windows.Interop.HwndSource> verknüpft:  
  
```  
source->RootVisual = page;  
```  
  
 In der letzten Zeile wird nun noch das HWND für die <xref:System.Windows.Interop.HwndSource> zurückgegeben:  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## Positionieren des HWNDs  
 Nachdem Sie jetzt ein HWND erstellt haben, das die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Uhr enthält, muss das HWND im [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Dialogfeld platziert werden.  Falls Sie genau wissen, an welcher Stelle das HWND positioniert werden soll, übergeben Sie einfach seine Größe und Position an die zuvor definierte `GetHwnd`\-Funktion.  Da Sie jedoch das Dialogfeld über eine Ressourcendatei definiert haben, können Sie nicht genau wissen, wo die einzelnen HWNDs positioniert sind.  Sie können mit dem Dialog\-Editor in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] ein [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-STATIC\-Steuerelement an der für die Uhr gewünschten Position einfügen \("Uhr hier einfügen"\) und dann die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Uhr mithilfe dieses Steuerelements platzieren.  
  
 Bei der Behandlung von WM\_INITDIALOG können Sie mit `GetDlgItem` das HWND für den STATIC\-Platzhalter abrufen:  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 Anschließend werden die Größe und die Position dieses STATIC\-Platzhalters berechnet, und die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Uhr wird an dieser Stelle eingefügt:  
  
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
  
 Jetzt blenden Sie den STATIC\-Platzhalter aus:  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 Und nun wird an dieser Stelle das HWND für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Uhr erstellt:  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 Damit dieses Lernprogramm für Sie interessanter wird und um eine echte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Uhr zu erstellen, müssen Sie an dieser Stelle ein Steuerelement für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Uhr erstellen.  Dies geschieht zum größten Teil mittels Markup mit nur einigen Ereignishandlern im Code\-Behind.  Da das Thema dieses Lernprogramms die Interoperation und nicht der Entwurf von Steuerelementen ist, wird der vollständige Code für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Uhr als Codeblock zur Verfügung gestellt, ohne weitere Informationen zum Aufbau und der Bedeutung der einzelnen Abschnitte.  Sie können gerne mit diesem Code experimentieren und die Darstellung und Funktionen des Steuerelements ändern.  
  
 Es folgt das Markup:  
  
 [!code-xml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 Und dies ist das zugehörige Code\-Behind:  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 Das Endergebnis sieht wie folgt aus:  
  
 ![Dialogfeld Datums&#45; und Uhrzeiteigenschaften](../../../../docs/framework/wpf/advanced/media/interoparch08.png "InteropArch08")  
  
 Wenn Sie Ihr Ergebnis mit dem Code für diese Abbildung vergleichen möchten, rufen Sie das Beispiel unter [Beispiel für die Win32\-Uhrinteroperation](http://go.microsoft.com/fwlink/?LinkID=160051) auf.  
  
## Siehe auch  
 <xref:System.Windows.Interop.HwndSource>   
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Beispiel für die Win32\-Uhrinteroperation](http://go.microsoft.com/fwlink/?LinkID=160051)