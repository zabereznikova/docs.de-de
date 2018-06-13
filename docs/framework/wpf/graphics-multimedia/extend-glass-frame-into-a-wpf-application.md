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
ms.openlocfilehash: 1e1efd6db6efa3a0b85d7d7794be7d3728da8c85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557510"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="37345-102">Erweitern von Glasframe in eine WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="37345-102">Extend Glass Frame Into a WPF Application</span></span>
<span data-ttu-id="37345-103">In diesem Thema veranschaulicht das Erweitern der [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] Glasframe in den Clientbereich des eine Windows Presentation Foundation (WPF)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="37345-103">This topic demonstrates how to extend the [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37345-104">Dieses Beispiel funktioniert nur auf einem [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]-Computer, auf dem Desktop Window Manager (DWM) mit aktiviertem Glaseffekt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="37345-104">This example will only work on a [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]<span data-ttu-id="37345-105"> Home Basic-Edition unterstützt den transparenten Glaseffekt nicht.</span><span class="sxs-lookup"><span data-stu-id="37345-105"> Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="37345-106">Bereiche, die in der Regel mit dem transparenten Glaseffekt in anderen Editionen von [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] gerendert werden, werden als nicht transparent gerendert.</span><span class="sxs-lookup"><span data-stu-id="37345-106">Areas that would typically render with the transparent glass effect on other editions of [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] are rendered opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37345-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37345-107">Example</span></span>  
 <span data-ttu-id="37345-108">Die folgende Abbildung zeigt den in der Adressleiste von Internet Explorer 7 erweiterten Glasframe.</span><span class="sxs-lookup"><span data-stu-id="37345-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="37345-109">**Internet Explorer mit erweitertem Glasframe hinter der Adressleiste.**</span><span class="sxs-lookup"><span data-stu-id="37345-109">**Internet Explorer with extended glass frame behind address bar.**</span></span>  
  
 <span data-ttu-id="37345-110">![IE7 mit sich hinter die Adressleiste ausdehnendem Glasframe](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")</span><span class="sxs-lookup"><span data-stu-id="37345-110">![IE7 with glass frame extended behind address bar.](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")</span></span>  
  
 <span data-ttu-id="37345-111">Um ein Glasframe auf einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung zu erweitern, benötige Sie Zugriff auf nicht verwaltete [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37345-111">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] is needed.</span></span> <span data-ttu-id="37345-112">Das folgende Codebeispiel führt einen Plattformaufruf (Pinvoke) für die beiden [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] durch, der erforderlich ist, um den Frame in den Clientbereich zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="37345-112">The following code example does a Platform Invoke (pinvoke) for the two [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] needed to extend the frame into the client area.</span></span> <span data-ttu-id="37345-113">Jede dieser [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] werden in einer Klasse namens **NonClientRegionAPI** deklariert.</span><span class="sxs-lookup"><span data-stu-id="37345-113">Each of these [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] are declared in a class called **NonClientRegionAPI**.</span></span>  
  
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
  
 <span data-ttu-id="37345-114">[DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) ist die DWM-Funktion, die den Frame in den Clientbereich erweitert.</span><span class="sxs-lookup"><span data-stu-id="37345-114">[DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="37345-115">Es werden zwei Parameter benötigt; ein Fensterhandle und eine [RÄNDER](https://msdn.microsoft.com/library/bb773244.aspx)-Struktur.</span><span class="sxs-lookup"><span data-stu-id="37345-115">It takes two parameters; a window handle and a [MARGINS](https://msdn.microsoft.com/library/bb773244.aspx) structure.</span></span> <span data-ttu-id="37345-116">[RÄNDER](https://msdn.microsoft.com/library/bb773244.aspx) wird verwendet, um den DWM zu zeigen, wie weit der Frame in den Clientbereich erweitert werden soll.</span><span class="sxs-lookup"><span data-stu-id="37345-116">[MARGINS](https://msdn.microsoft.com/library/bb773244.aspx) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37345-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37345-117">Example</span></span>  
 <span data-ttu-id="37345-118">Ein Fensterhandle muss abgerufen werden, damit die [DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx)-Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="37345-118">To use the [DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) function, a window handle must be obtained.</span></span> <span data-ttu-id="37345-119">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], das Fensterhandle abgerufen werden kann, aus der <xref:System.Windows.Interop.HwndSource.Handle%2A> Eigenschaft ein <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="37345-119">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="37345-120">Im folgenden Beispiel der Frame auf in den Clientbereich erweitert die <xref:System.Windows.FrameworkElement.Loaded> Ereignis des Fensters.</span><span class="sxs-lookup"><span data-stu-id="37345-120">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="37345-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37345-121">Example</span></span>  
 <span data-ttu-id="37345-122">Das folgende Beispiel zeigt ein einfaches Fenster, in dem der Frame in den Clientbereich erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="37345-122">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="37345-123">Der Frame wird hinter dem oberen Rand, die die beiden enthält erweitert <xref:System.Windows.Controls.TextBox> Objekte.</span><span class="sxs-lookup"><span data-stu-id="37345-123">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>  
  
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
  
 <span data-ttu-id="37345-124">Die folgende Abbildung zeigt den in eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung erweiterten Glasframe.</span><span class="sxs-lookup"><span data-stu-id="37345-124">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application.</span></span>  
  
 <span data-ttu-id="37345-125">**In eine** [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]**-Anwendung erweiterter Glasframe.**</span><span class="sxs-lookup"><span data-stu-id="37345-125">**Glass Frame Extended into a**  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]  **Application.**</span></span>  
  
 <span data-ttu-id="37345-126">![In eine WPF-Anwendung erweiterter Glasframe.](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span><span class="sxs-lookup"><span data-stu-id="37345-126">![Glass Frame Extended into a WPF application.](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37345-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37345-127">See Also</span></span>  
 [<span data-ttu-id="37345-128">Desktopfenster-Manager (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="37345-128">Desktop Window Manager Overview</span></span>](https://msdn.microsoft.com/library/aa969540.aspx)  
 [<span data-ttu-id="37345-129">Übersicht über die Blur Desktopfenster-Manager</span><span class="sxs-lookup"><span data-stu-id="37345-129">Desktop Window Manager Blur Overview</span></span>](https://msdn.microsoft.com/library/aa969537.aspx)  
 [<span data-ttu-id="37345-130">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="37345-130">DwmExtendFrameIntoClientArea</span></span>](https://msdn.microsoft.com/library/aa969512.aspx)
