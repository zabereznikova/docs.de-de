---
title: Erweitern von Glasframe in eine WPF-Anwendung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
ms.openlocfilehash: ae4d7f23729f5bd39558902a58d33c6c45572d85
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977019"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="d89df-102">Erweitern von Glasframe in eine WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d89df-102">Extend Glass Frame Into a WPF Application</span></span>

<span data-ttu-id="d89df-103">In diesem Thema wird veranschaulicht, wie Sie den Windows Vista-Glasframe in den Client Bereich einer Windows Presentation Foundation (WPF)-Anwendung erweitern.</span><span class="sxs-lookup"><span data-stu-id="d89df-103">This topic demonstrates how to extend the Windows Vista glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>

> [!NOTE]
> <span data-ttu-id="d89df-104">Dieses Beispiel funktioniert nur auf einem Windows Vista-Computer, auf dem die Desktopfenster-Manager (DWM) mit aktiviertem Glas ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d89df-104">This example will only work on a Windows Vista machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> <span data-ttu-id="d89df-105">Windows Vista Home Basic Edition unterstützt den transparenten Glas Effekt nicht.</span><span class="sxs-lookup"><span data-stu-id="d89df-105">Windows Vista Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="d89df-106">Bereiche, die in der Regel mit dem transparenten Glas Effekt für andere Editionen von Windows Vista gerendert werden, sind nicht transparent.</span><span class="sxs-lookup"><span data-stu-id="d89df-106">Areas that would typically render with the transparent glass effect on other editions of Windows Vista are rendered opaque.</span></span>

## <a name="example"></a><span data-ttu-id="d89df-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d89df-107">Example</span></span>

<span data-ttu-id="d89df-108">Die folgende Abbildung veranschaulicht den Glasframe, der in der Adressleiste von Internet Explorer 7 erweitert wurde:</span><span class="sxs-lookup"><span data-stu-id="d89df-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7:</span></span>

![Screenshot mit einem Glasrahmen, der hinter der IE7-Adressleiste erweitert ist](./media/extend-glass-frame-into-a-wpf-application/internet-explorer-glass-frame-extended-address-bar.png)

<span data-ttu-id="d89df-110">Um den Glasframe in einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung zu erweitern, wird der Zugriff auf die nicht verwaltete API benötigt.</span><span class="sxs-lookup"><span data-stu-id="d89df-110">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged API is needed.</span></span> <span data-ttu-id="d89df-111">Im folgenden Codebeispiel wird ein Platt Form Aufruf (PInvoke) für die beiden APIs durchführt, die benötigt werden, um den Frame in den Client Bereich zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d89df-111">The following code example does a Platform Invoke (pinvoke) for the two API needed to extend the frame into the client area.</span></span> <span data-ttu-id="d89df-112">Jede dieser APIs wird in einer Klasse mit dem Namen **NonClientRegionAPI**deklariert.</span><span class="sxs-lookup"><span data-stu-id="d89df-112">Each of these API are declared in a class called **NonClientRegionAPI**.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential)]
public struct MARGINS
{
    public int cxLeftWidth;      // width of left border that retains its size
    public int cxRightWidth;     // width of right border that retains its size
    public int cyTopHeight;      // height of top border that retains its size
    public int cyBottomHeight;   // height of bottom border that retains its size
};

[DllImport("DwmApi.dll")]
public static extern int DwmExtendFrameIntoClientArea(
    IntPtr hwnd,
    ref MARGINS pMarInset);
```

```vb
<StructLayout(LayoutKind.Sequential)>
Public Structure MARGINS
    Public cxLeftWidth As Integer ' width of left border that retains its size
    Public cxRightWidth As Integer ' width of right border that retains its size
    Public cyTopHeight As Integer ' height of top border that retains its size
    Public cyBottomHeight As Integer ' height of bottom border that retains its size
End Structure

<DllImport("DwmApi.dll")>
Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer
End Function
```

<span data-ttu-id="d89df-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) ist die DWM-Funktion, die den Frame in den Clientbereich erweitert.</span><span class="sxs-lookup"><span data-stu-id="d89df-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="d89df-114">Es werden zwei Parameter benötigt; ein Fensterhandle und eine [RÄNDER](/windows/win32/api/uxtheme/ns-uxtheme-margins)-Struktur.</span><span class="sxs-lookup"><span data-stu-id="d89df-114">It takes two parameters; a window handle and a [MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) structure.</span></span> <span data-ttu-id="d89df-115">[RÄNDER](/windows/win32/api/uxtheme/ns-uxtheme-margins) wird verwendet, um den DWM zu zeigen, wie weit der Frame in den Clientbereich erweitert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d89df-115">[MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>

## <a name="example"></a><span data-ttu-id="d89df-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d89df-116">Example</span></span>

<span data-ttu-id="d89df-117">Ein Fensterhandle muss abgerufen werden, damit die [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)-Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d89df-117">To use the [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) function, a window handle must be obtained.</span></span> <span data-ttu-id="d89df-118">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]kann das Fenster Handle aus der <xref:System.Windows.Interop.HwndSource.Handle%2A>-Eigenschaft eines <xref:System.Windows.Interop.HwndSource>abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d89df-118">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="d89df-119">Im folgenden Beispiel wird der Frame in den Client Bereich auf dem <xref:System.Windows.FrameworkElement.Loaded>-Ereignis des-Fensters erweitert.</span><span class="sxs-lookup"><span data-stu-id="d89df-119">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>

```csharp
void OnLoaded(object sender, RoutedEventArgs e)
{
   try
   {
      // Obtain the window handle for WPF application
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);

      // Get System Dpi
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);
      float DesktopDpiX = desktop.DpiX;
      float DesktopDpiY = desktop.DpiY;

      // Set Margins
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();

      // Extend glass frame into client area
      // Note that the default desktop Dpi is 96dpi. The  margins are
      // adjusted for the system Dpi.
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));

      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);
      //
      if (hr < 0)
      {
         //DwmExtendFrameIntoClientArea Failed
      }
   }
   // If not Vista, paint background white.
   catch (DllNotFoundException)
   {
      Application.Current.MainWindow.Background = Brushes.White;
   }
}
```

## <a name="example"></a><span data-ttu-id="d89df-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d89df-120">Example</span></span>

<span data-ttu-id="d89df-121">Das folgende Beispiel zeigt ein einfaches Fenster, in dem der Frame in den Clientbereich erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="d89df-121">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="d89df-122">Der Frame wird hinter dem oberen Rand erweitert, der die beiden <xref:System.Windows.Controls.TextBox> Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="d89df-122">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>

```xaml
<Window x:Class="SDKSample.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Extended Glass in WPF" Height="300" Width="400"
    Loaded="OnLoaded" Background="Transparent"
    >
  <Grid ShowGridLines="True">
    <DockPanel Name="mainDock">
      <!-- The border is used to compute the rendered height with margins.
           topBar contents will be displayed on the extended glass frame.-->
      <Border Name="topBar" DockPanel.Dock="Top" >
        <Grid Name="grid">
          <Grid.ColumnDefinitions>
            <ColumnDefinition MinWidth="100" Width="*"/>
            <ColumnDefinition Width="Auto"/>
          </Grid.ColumnDefinitions>
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>
        </Grid>
      </Border>
      <Grid DockPanel.Dock="Top" >
        <Grid.ColumnDefinitions>
          <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <TextBox Grid.Column="0" AcceptsReturn="True"/>
      </Grid>
    </DockPanel>
  </Grid>
</Window>
```

<span data-ttu-id="d89df-123">Die folgende Abbildung veranschaulicht den in eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung erweiterten Glasframe:</span><span class="sxs-lookup"><span data-stu-id="d89df-123">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application:</span></span>

![Screenshot, der einen in eine WPF-Anwendung erweiterten Glasframe zeigt](./media/extend-glass-frame-into-a-wpf-application/glass-frame-extended-wpf-application.png)

## <a name="see-also"></a><span data-ttu-id="d89df-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d89df-125">See also</span></span>

- [<span data-ttu-id="d89df-126">Übersicht über Desktopfenster-Manager</span><span class="sxs-lookup"><span data-stu-id="d89df-126">Desktop Window Manager Overview</span></span>](/windows/desktop/dwm/dwm-overview)
- [<span data-ttu-id="d89df-127">Übersicht über Desktopfenster-Manager Unschärfe</span><span class="sxs-lookup"><span data-stu-id="d89df-127">Desktop Window Manager Blur Overview</span></span>](/windows/desktop/dwm/blur-ovw)
- [<span data-ttu-id="d89df-128">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="d89df-128">DwmExtendFrameIntoClientArea</span></span>](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)
