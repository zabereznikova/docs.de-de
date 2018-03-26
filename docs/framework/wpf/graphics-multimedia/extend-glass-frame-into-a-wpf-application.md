---
title: Erweitern von Glasframe in eine WPF-Anwendung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aad070bca408fc608eb000948c1b942d08f02018
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2018
---
# <a name="extend-glass-frame-into-a-wpf-application"></a>Erweitern von Glasframe in eine WPF-Anwendung
Dieses Thema veranschaulicht das Erweitern der [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]-Glasframe in den Clientbereich einer [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]-Anwendung.  
  
> [!NOTE]
>  Dieses Beispiel funktioniert nur auf einem [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]-Computer, auf dem Desktop Window Manager (DWM) mit aktiviertem Glaseffekt ausgeführt wird. [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] Home Basic-Edition unterstützt den transparenten Glaseffekt nicht. Bereiche, die in der Regel mit dem transparenten Glaseffekt in anderen Editionen von [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] gerendert werden, werden als nicht transparent gerendert.  
  
## <a name="example"></a>Beispiel  
 Die folgende Abbildung zeigt den in der Adressleiste von Internet Explorer 7 erweiterten Glasframe.  
  
 **Internet Explorer mit erweitertem Glasframe hinter der Adressleiste.**  
  
 ![IE7 mit sich hinter die Adressleiste ausdehnendem Glasframe](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")  
  
 Um ein Glasframe auf einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung zu erweitern, benötige Sie Zugriff auf nicht verwaltete [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]. Das folgende Codebeispiel führt einen Plattformaufruf (Pinvoke) für die beiden [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] durch, der erforderlich ist, um den Frame in den Clientbereich zu erweitern. Jede dieser [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] werden in einer Klasse namens **NonClientRegionAPI** deklariert.  
  
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
  
 [DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) ist die DWM-Funktion, die den Frame in den Clientbereich erweitert. Es werden zwei Parameter benötigt; ein Fensterhandle und eine [RÄNDER](https://msdn.microsoft.com/library/bb773244.aspx)-Struktur. [RÄNDER](https://msdn.microsoft.com/library/bb773244.aspx) wird verwendet, um den DWM zu zeigen, wie weit der Frame in den Clientbereich erweitert werden soll.  
  
## <a name="example"></a>Beispiel  
 Ein Fensterhandle muss abgerufen werden, damit die [DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx)-Funktion verwendet werden kann. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], das Fensterhandle abgerufen werden kann, aus der <xref:System.Windows.Interop.HwndSource.Handle%2A> Eigenschaft ein <xref:System.Windows.Interop.HwndSource>. Im folgenden Beispiel der Frame auf in den Clientbereich erweitert die <xref:System.Windows.FrameworkElement.Loaded> Ereignis des Fensters.  
  
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
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein einfaches Fenster, in dem der Frame in den Clientbereich erweitert wird. Der Frame wird hinter dem oberen Rand, die die beiden enthält erweitert <xref:System.Windows.Controls.TextBox> Objekte.  
  
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
  
 Die folgende Abbildung zeigt den in eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung erweiterten Glasframe.  
  
 **In eine** [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]**-Anwendung erweiterter Glasframe.**  
  
 ![In eine WPF-Anwendung erweiterter Glasframe.](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")  
  
## <a name="see-also"></a>Siehe auch  
 [Desktopfenster-Manager (Übersicht)](https://msdn.microsoft.com/library/aa969540.aspx)  
 [Übersicht über die Blur Desktopfenster-Manager](https://msdn.microsoft.com/library/aa969537.aspx)  
 [DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx)
