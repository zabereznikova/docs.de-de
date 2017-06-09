---
title: "Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfl&#228;che ist | Microsoft Docs"
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
  - "Erstellen eines Add-Ins als Benutzeroberfläche [WPF]"
  - "-Add-ins [WPF] Benutzeroberfläche"
  - "Erstellen eines Benutzeroberflächen-Add-Ins [WPF]"
  - "Benutzeroberflächen-add-ins [WPF], erstellen"
  - "Implementieren von Benutzeroberflächen-Add-Ins [WPF]"
  - "Erstellen von Add-Ins Pipelinesegmente [WPF]"
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfl&#228;che ist
\<?xml version="1.0" encoding="utf-8"?>
\<developerHowToDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>Dieses Beispiel zeigt, wie Sie ein Add-in erstellen, ist ein <token>TLA #Tla_wpf</token> <token>TLA #Tla_ui</token> die gehostet wird ein <token>TLA&#2;Tla_wpf</token> eigenständige Anwendung.</para> 
    <para>Das Add-in ist eine <token>TLA&#2;Tla_ui</token> , ein <token>TLA&#2;Tla_wpf</token> Benutzersteuerelement. Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche geklickt haben, wird ein Meldungsfeld angezeigt. Die <token>TLA&#2;Tla_wpf</token> eigenständige Anwendung hostet das Add-in <token>TLA&#2;Tla_ui</token> als Inhalt des Hauptfensters der Anwendung.</para> 
    <para> 
      <embeddedLabel>Erforderlichen Komponenten</embeddedLabel>
    </para>
    <para>in diesem Beispiel hebt die <token>TLA&#2;Tla_wpf</token> Erweiterungen für die <token>Dnprdnshort</token> Add-In-Modell, mit denen dieses Szenario und die folgenden:</para>
    <list class="bullet">
      <listItem>
        <para>Kenntnisse der <token>Dnprdnshort</token> Add-In-Modell, einschließlich der Pipeline-add-in und Hostentwicklung. Wenn Sie mit diesen Konzepten nicht vertraut sind, finden Sie unter \<legacyLink xlink:href="8dd45b02-7218-40f9-857d-40d7b98b850b">Add-Ins und Erweiterbarkeit</legacyLink>. Ein Lernprogramm, das die Implementierung einer Pipeline, ein Add-in und Host-Anwendung veranschaulicht, finden Sie unter \<legacyLink xlink:href="694a33c5-a040-450d-aed5-ac49fc88ce61">Exemplarische Vorgehensweise: Erstellen einer erweiterbaren Anwendung</legacyLink>.</para> 
      </listItem> 
      <listItem> 
        <para>Kenntnisse der <token>TLA&#2;Tla_wpf</token> -Erweiterungen für die <token>Dnprdnshort</token> Add-In-Modell, das hier befindet: \<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">Übersicht über WPF-Add-Ins</link>.</para> 
      </listItem> 
    </list> 
  </introduction> 
  <codeExample> 
    <legacy> 
      <content> 
        <para>, Ein Add-in zu erstellen, ist ein <token>TLA&#2;Tla_wpf</token> <token>TLA&#2;Tla_ui</token> spezifischen Code für jedes Pipelinesegment, das Add-in und Host-Anwendung erfordert.</para> 
        <para> 
          <token>AutoOutline</token>
        </para>
      </content>
      <sections>
        <section address="Contract">
          <title>Implementieren der Pipeline Vertragssegment</title>
          <content>
            <para>Wenn ein Add-in ist eine <token>TLA&#2;Tla_ui</token>, muss der Vertrag für das Add-In implementieren <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference>. Im Beispiel <codeInline>IWPFAddInContract</codeInline> implementiert <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference>, wie im folgenden Code gezeigt.</para>
            <code language="c#">using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // AddInContractAttribute

namespace Contracts
{
    /// &lt;summary&gt;
    /// Defines the services that an add-in will provide to a host application.
    /// In this case, the add-in is a UI.
    /// &lt;/summary&gt;
    [AddInContract]
    public interface IWPFAddInContract : INativeHandleContract {}
}</code>
          <code language="vb">Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' AddInContractAttribute

Namespace Contracts
    ''' &lt;summary&gt;
    ''' Defines the services that an add-in will provide to a host application.
    ''' In this case, the add-in is a UI.
    ''' &lt;/summary&gt;
    &lt;AddInContract&gt;
    Public Interface IWPFAddInContract
        Inherits INativeHandleContract
        Inherits IContract
    End Interface
End Namespace</code></content>
        </section>
        <section address="AddInViewPipeline">
          <title>Implementieren die Add-In-Ansicht Pipeline Segment</title>
          <content>
            <para>da das Add-in, als eine Unterklasse von implementiert wird der <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> Typ der Add-In-Ansicht muss auch als Unterklasse <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference>. Der folgende Code zeigt die Add-In-Ansicht des Vertrags, als implementiert die <codeInline>WPFAddInView</codeInline> Klasse</para> 
            <code language="c#">using System.AddIn.Pipeline; // AddInBaseAttribute
using System.Windows.Controls; // UserControl

namespace AddInViews
{
    /// &lt;summary&gt;
    /// Defines the add-in's view of the contract.
    /// &lt;/summary&gt;
    [AddInBase]
    public class WPFAddInView : UserControl { }
}</code> 
          <code language="vb">Imports System.AddIn.Pipeline ' AddInBaseAttribute
Imports System.Windows.Controls ' UserControl

Namespace AddInViews
    ''' &lt;summary&gt;
    ''' Defines the add-in's view of the contract.
    ''' &lt;/summary&gt;
    &lt;AddInBase&gt;
    Public Class WPFAddInView
        Inherits UserControl
    End Class
End Namespace</code> 
            <para>Hier die Add-In Ansicht abgeleitet ist <codeEntityReference autoUpgrade="true">System.Windows.Controls.UserControl</codeEntityReference>. Aus diesem Grund die Add-in- <token>TLA&#2;Tla_ui</token> sollten auch abgeleitet <codeEntityReference autoUpgrade="true">System.Windows.Controls.UserControl</codeEntityReference>.</para>
          </content>
        </section>
        <section address="AddInSideAdapter">
          <title>Implementieren der Add-In-Side Adapterpipelinesegments</title>
          <content>
            <para>während der Vertrag ist eine <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference>, Add-in ist eine <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> (wie durch die Add-In-Ansicht Pipelinesegment angegeben). Aus diesem Grund die <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> konvertiert werden muss, um eine <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference> vor dem Überschreiten der Isolationsgrenze. Dieser Vorgang wird durch Aufrufen der Add-In-seitige Adapter ausgeführt <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference>, wie im folgenden Code gezeigt.</para> 
            <code language="c#">using System; // IntPtr
using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // AddInAdapterAttribute, FrameworkElementAdapters, ContractBase
using System.Security.Permissions;

using AddInViews; // WPFAddInView
using Contracts; // IWPFAddInContract

namespace AddInSideAdapters
{
    /// &lt;summary&gt;
    /// Adapts the add-in's view of the contract to the add-in contract
    /// &lt;/summary&gt;
    [AddInAdapter]
    public class WPFAddIn_ViewToContractAddInSideAdapter : ContractBase, IWPFAddInContract
    {
        WPFAddInView wpfAddInView;

        public WPFAddIn_ViewToContractAddInSideAdapter(WPFAddInView wpfAddInView)
        {
            // Adapt the add-in view of the contract (WPFAddInView) 
            // to the contract (IWPFAddInContract)
            this.wpfAddInView = wpfAddInView;
        }

        /// &lt;summary&gt;
        /// ContractBase.QueryContract must be overridden to:
        /// * Safely return a window handle for an add-in UI to the host 
        ///   application's application.
        /// * Enable tabbing between host application UI and add-in UI, in the
        ///   "add-in is a UI" scenario.
        /// &lt;/summary&gt;
        public override IContract QueryContract(string contractIdentifier)
        {
            if (contractIdentifier.Equals(typeof(INativeHandleContract).AssemblyQualifiedName))
            {
                return FrameworkElementAdapters.ViewToContractAdapter(this.wpfAddInView);
            }

            return base.QueryContract(contractIdentifier);
        }

        /// &lt;summary&gt;
        /// GetHandle is called by the WPF add-in model from the host application's 
        /// application domain to to get the window handle for an add-in UI from the 
        /// add-in's application domain. GetHandle is called if a window handle isn't 
        /// returned by other means ie overriding ContractBase.QueryContract, 
        /// as shown above.
        /// NOTE: This method requires UnmanagedCodePermission to be called 
        ///       (full-trust by default), to prevent illegal window handle
        ///       access in partially trusted scenarios. If the add-in could
        ///       run in a partially trusted application domain 
        ///       (eg AddInSecurityLevel.Internet), you can safely return a window
        ///       handle by overriding ContractBase.QueryContract, as shown above.
        /// &lt;/summary&gt;
        [SecurityPermissionAttribute(SecurityAction.Demand, Flags = SecurityPermissionFlag.UnmanagedCode)]
        public IntPtr GetHandle()
        {
            return FrameworkElementAdapters.ViewToContractAdapter(this.wpfAddInView).GetHandle();
        }
    }
}</code> 
          <code language="vb">Imports System ' IntPtr
Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' AddInAdapterAttribute, FrameworkElementAdapters, ContractBase
Imports System.Security.Permissions

Imports AddInViews ' WPFAddInView
Imports Contracts ' IWPFAddInContract

Namespace AddInSideAdapters
    ''' &lt;summary&gt;
    ''' Adapts the add-in's view of the contract to the add-in contract
    ''' &lt;/summary&gt;
    &lt;AddInAdapter&gt;
    Public Class WPFAddIn_ViewToContractAddInSideAdapter
        Inherits ContractBase
        Implements IWPFAddInContract

        Private wpfAddInView As WPFAddInView

        Public Sub New(ByVal wpfAddInView As WPFAddInView)
            ' Adapt the add-in view of the contract (WPFAddInView) 
            ' to the contract (IWPFAddInContract)
            Me.wpfAddInView = wpfAddInView
        End Sub

        ''' &lt;summary&gt;
        ''' ContractBase.QueryContract must be overridden to:
        ''' * Safely return a window handle for an add-in UI to the host 
        '''   application's application.
        ''' * Enable tabbing between host application UI and add-in UI, in the
        '''   "add-in is a UI" scenario.
        ''' &lt;/summary&gt;
        Public Overrides Function QueryContract(ByVal contractIdentifier As String) As IContract
            If contractIdentifier.Equals(GetType(INativeHandleContract).AssemblyQualifiedName) Then
                Return FrameworkElementAdapters.ViewToContractAdapter(Me.wpfAddInView)
            End If

            Return MyBase.QueryContract(contractIdentifier)
        End Function

        ''' &lt;summary&gt;
        ''' GetHandle is called by the WPF add-in model from the host application's 
        ''' application domain to to get the window handle for an add-in UI from the 
        ''' add-in's application domain. GetHandle is called if a window handle isn't 
        ''' returned by other means ie overriding ContractBase.QueryContract, 
        ''' as shown above.
        ''' NOTE: This method requires UnmanagedCodePermission to be called 
        '''       (full-trust by default), to prevent illegal window handle
        '''       access in partially trusted scenarios. If the add-in could
        '''       run in a partially trusted application domain 
        '''       (eg AddInSecurityLevel.Internet), you can safely return a window
        '''       handle by overriding ContractBase.QueryContract, as shown above.
        ''' &lt;/summary&gt;
        &lt;SecurityPermissionAttribute(SecurityAction.Demand, Flags:=SecurityPermissionFlag.UnmanagedCode)&gt;
        Public Function GetHandle() As IntPtr Implements INativeHandleContract.GetHandle
            Return FrameworkElementAdapters.ViewToContractAdapter(Me.wpfAddInView).GetHandle()
        End Function

    End Class
End Namespace</code> 
            <para>In die Add-In-Modell, in dem ein Add-in gibt, eine <token>TLA&#2;Tla_ui</token> (finden Sie unter \<link xlink:href="57f274b7-4c66-4b72-92eb-81939a393776">wie: Erstellen Sie ein Add-in, gibt eine Benutzeroberfläche</link>), konvertiert die Add-in-Adapter die <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> auf ein <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference> durch Aufrufen von <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference>. <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference> muss ebenfalls in diesem Modell aufgerufen werden, obwohl Sie schreiben den Code zum Aufrufen der Methode implementieren müssen. Überschreiben Sie dazu <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> und den aufrufende Code implementieren <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference> Wenn der Code, der den Aufruf <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> erwartet ein <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference>. In diesem Fall wird der Aufrufer der hostseitige Adapter sein, die in einem nachfolgenden Unterabschnitt behandelt wird.</para>
            <alert class="note">
              <para> Sie müssen auch überschreiben <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> in diesem Modell aktivieren Wechsel zwischen Host-Anwendung <token>TLA&#2;Tla_ui</token> und Add-in- <token>TLA&#2;Tla_ui</token>. Weitere Informationen finden Sie in "WPF-Add-In" in \<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">Übersicht über WPF-Add-Ins</link>.</para> 
            </alert> 
            <para>Da der Add-In-seitige Adapter eine Schnittstelle, die implementiert von abgeleitet <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference>, müssen Sie auch implementieren <codeEntityReference autoUpgrade="true">m: System.AddIn.Contract.INativeHandleContract.getHandle</codeEntityReference>, obwohl dies ignoriert beim <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> überschrieben wird.</para>
          </content>
        </section>
        <section address="HostViewPipeline">
          <title>Implementieren des Host-Ansichtspipelinesegments</title>
          <content>
            <para>In diesem Modell die Host-Anwendung in der Regel werden die Hostansicht erwartet ein <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> Unterklasse. Der hostseitige Adapter muss umwandeln, die <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference> zu einer <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> nach der <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference> überschreitet die Isolationsgrenze. Da eine Methode vom hostanwendung aufgerufen wird, ist nicht der <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference>, die Hostansicht muss "return" die <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> von enthalten ist. Daher muss die Hostansicht ableiten, einer Unterklasse von <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> enthalten können andere <token>TLA&#2;Tla_ui #plural</token>, wie z. B. <codeEntityReference autoUpgrade="true">System.Windows.Controls.UserControl</codeEntityReference>. Der folgende Code zeigt die Hostansicht des Vertrags, als implementiert die <codeInline>WPFAddInHostView</codeInline> Klasse.</para>
            <code language="c#">using System.Windows.Controls; // UserControl

namespace HostViews
{
    /// &lt;summary&gt;
    /// Defines the host's view of the add-in
    /// &lt;/summary&gt;
    public class WPFAddInHostView : UserControl { }
}</code>
          <code language="vb">Imports System.Windows.Controls ' UserControl

Namespace HostViews
    ''' &lt;summary&gt;
    ''' Defines the host's view of the add-in
    ''' &lt;/summary&gt;
    Public Class WPFAddInHostView
        Inherits UserControl
    End Class
End Namespace</code>
          </content>
        </section>
        <section address="HostSideAdapter">
          <title>Implementieren der hostseitige Adapter Pipeline Segment</title>
          <content>
            <para>während der Vertrag ist eine <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference>, die hostanwendung erwartet einen <codeEntityReference autoUpgrade="true">System.Windows.Controls.UserControl</codeEntityReference> (wie durch die Hostansicht angegeben). Folglich die <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference> muss konvertiert werden, um eine <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> nach dem Überschreiten der Isolationsgrenze, bevor er als Inhalt der Hostansicht festgelegt (abgeleitet, das von <codeEntityReference autoUpgrade="true">System.Windows.Controls.UserControl</codeEntityReference>).</para> 
            <para>Dieser Vorgang wird der hostseitige Adapter ausgeführt, wie im folgenden Code gezeigt. </para> 
            <code language="c#">using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // HostAdapterAttribute, FrameworkElementAdapters, ContractHandle
using System.Windows; // FrameworkElement

using Contracts; // IWPFAddInContract
using HostViews; // WPFAddInHostView

namespace HostSideAdapters
{
    /// &lt;summary&gt;
    /// Adapts the add-in contract to the host's view of the add-in
    /// &lt;/summary&gt;
    [HostAdapter]
    public class WPFAddIn_ContractToViewHostSideAdapter : WPFAddInHostView
    {
        IWPFAddInContract wpfAddInContract;
        ContractHandle wpfAddInContractHandle;

        public WPFAddIn_ContractToViewHostSideAdapter(IWPFAddInContract wpfAddInContract)
        {
            // Adapt the contract (IWPFAddInContract) to the host application's
            // view of the contract (WPFAddInHostView)
            this.wpfAddInContract = wpfAddInContract;

            // Prevent the reference to the contract from being released while the
            // host application uses the add-in
            this.wpfAddInContractHandle = new ContractHandle(wpfAddInContract);

            // Convert the INativeHandleContract for the add-in UI that was passed 
            // from the add-in side of the isolation boundary to a FrameworkElement
            string aqn = typeof(INativeHandleContract).AssemblyQualifiedName;
            INativeHandleContract inhc = (INativeHandleContract)wpfAddInContract.QueryContract(aqn);
            FrameworkElement fe = (FrameworkElement)FrameworkElementAdapters.ContractToViewAdapter(inhc);

            // Add FrameworkElement (which displays the UI provided by the add-in) as
            // content of the view (a UserControl)
            this.Content = fe;
        }
    }
}</code> 
          <code language="vb">Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' HostAdapterAttribute, FrameworkElementAdapters, ContractHandle
Imports System.Windows ' FrameworkElement

Imports Contracts ' IWPFAddInContract
Imports HostViews ' WPFAddInHostView

Namespace HostSideAdapters
    ''' &lt;summary&gt;
    ''' Adapts the add-in contract to the host's view of the add-in
    ''' &lt;/summary&gt;
    &lt;HostAdapter&gt;
    Public Class WPFAddIn_ContractToViewHostSideAdapter
        Inherits WPFAddInHostView
        Private wpfAddInContract As IWPFAddInContract
        Private wpfAddInContractHandle As ContractHandle

        Public Sub New(ByVal wpfAddInContract As IWPFAddInContract)
            ' Adapt the contract (IWPFAddInContract) to the host application's
            ' view of the contract (WPFAddInHostView)
            Me.wpfAddInContract = wpfAddInContract

            ' Prevent the reference to the contract from being released while the
            ' host application uses the add-in
            Me.wpfAddInContractHandle = New ContractHandle(wpfAddInContract)

            ' Convert the INativeHandleContract for the add-in UI that was passed 
            ' from the add-in side of the isolation boundary to a FrameworkElement
            Dim aqn As String = GetType(INativeHandleContract).AssemblyQualifiedName
            Dim inhc As INativeHandleContract = CType(wpfAddInContract.QueryContract(aqn), INativeHandleContract)
            Dim fe As FrameworkElement = CType(FrameworkElementAdapters.ContractToViewAdapter(inhc), FrameworkElement)

            ' Add FrameworkElement (which displays the UI provided by the add-in) as
            ' content of the view (a UserControl)
            Me.Content = fe
        End Sub
    End Class
End Namespace</code> 
            <para>Wie Sie sehen, der hostseitige Adapter Ruft die <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference> durch Aufrufen des Add-In-seitige Adapters <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> Methode (an diesem Punkt wird, in dem die <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference> überschreitet die Isolationsgrenze).</para> 
            <para>Der hostseitige Adapter konvertiert dann die <codeEntityReference autoUpgrade="true">: System.AddIn.Contract.INativeHandleContract</codeEntityReference> zu einer <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> durch Aufrufen von <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter(System.AddIn.Contract.INativeHandleContract)</codeEntityReference>. Abschließend die <codeEntityReference autoUpgrade="true">: System.Windows.FrameworkElement</codeEntityReference> als Inhalt der Hostansicht festgelegt ist.</para>
          </content>
        </section>
        <section address="AddIn">
          <title>Implementieren von Add-in-</title>
          <content>
            <para>mit dem Add-In-seitige Adapter und die Add-In-Ansicht, das Add-In implementiert werden kann durch Ableiten von der Add-In-Ansicht wie im folgenden Code gezeigt.</para> 
            <code language="xaml">&lt;addInViews:WPFAddInView
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:addInViews="clr-namespace:AddInViews;assembly=AddInViews"
    x:Class="WPFAddIn1.AddInUI"&gt;

    &lt;Grid&gt;
        &lt;Button Click="clickMeButton_Click" Content="Click Me!" /&gt;        
    &lt;/Grid&gt;

&lt;/addInViews:WPFAddInView&gt;</code> 
            <code language="c#">using System.AddIn; // AddInAttribute
using System.Windows; // MessageBox, RoutedEventArgs

using AddInViews; // WPFAddInView

namespace WPFAddIn1
{
    /// &lt;summary&gt;
    /// Implements the add-in by deriving from WPFAddInView
    /// &lt;/summary&gt;
    [AddIn("WPF Add-In 1")]
    public partial class AddInUI : WPFAddInView
    {
        public AddInUI()
        {
            InitializeComponent();
        }

        void clickMeButton_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Hello from WPFAddIn1");
        }
    }
}</code> 
          <code language="vb">Imports System.AddIn ' AddInAttribute
Imports System.Windows ' MessageBox, RoutedEventArgs

Imports AddInViews ' WPFAddInView

Namespace WPFAddIn1
    ''' &lt;summary&gt;
    ''' Implements the add-in by deriving from WPFAddInView
    ''' &lt;/summary&gt;
    &lt;AddIn("WPF Add-In 1")&gt;
    Partial Public Class AddInUI
        Inherits WPFAddInView
        Public Sub New()
            InitializeComponent()
        End Sub

        Private Sub clickMeButton_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
            MessageBox.Show("Hello from WPFAddIn1")
        End Sub
    End Class
End Namespace</code> 
            <para>Aus diesem Beispiel sehen Sie einen interessanten Vorteil dieses Modells: Add-In-Entwickler müssen nur das Add-In implementieren (da dies ist die <token>TLA&#2;Tla_ui</token> sowie), anstatt eine Add-in Klasse und ein Add-in <token>TLA&#2;Tla_ui</token>.</para>
          </content>
        </section>
        <section address="HostApp">
          <title>Implementieren der Hostanwendung</title>
          <content>
            <para>der hostseitige Adapter und der Hostansicht erstellt, die Host-Anwendung können die <token>Dnprdnshort</token> Add-In-Modell, um die Pipeline öffnen und eine Hostansicht des Add-Ins zu erwerben. Diese Schritte werden im folgenden Code dargestellt. </para> 
            <code language="c#">// Get add-in pipeline folder (the folder in which this application was launched from)
string appPath = Environment.CurrentDirectory;

// Rebuild visual add-in pipeline
string[] warnings = AddInStore.Rebuild(appPath);
if (warnings.Length &gt; 0)
{
    string msg = "Could not rebuild pipeline:";
    foreach (string warning in warnings) msg += "\n" + warning;
    MessageBox.Show(msg);
    return;
}

// Activate add-in with Internet zone security isolation
Collection&lt;AddInToken&gt; addInTokens = AddInStore.FindAddIns(typeof(WPFAddInHostView), appPath);
AddInToken wpfAddInToken = addInTokens[0];
this.wpfAddInHostView = wpfAddInToken.Activate&lt;WPFAddInHostView&gt;(AddInSecurityLevel.Internet);

// Display add-in UI
this.addInUIHostGrid.Children.Add(this.wpfAddInHostView);</code> 
          <code language="vb">' Get add-in pipeline folder (the folder in which this application was launched from)
Dim appPath As String = Environment.CurrentDirectory

' Rebuild visual add-in pipeline
Dim warnings() As String = AddInStore.Rebuild(appPath)
If warnings.Length &gt; 0 Then
    Dim msg As String = "Could not rebuild pipeline:"
    For Each warning As String In warnings
        msg &amp;= vbLf &amp; warning
    Next warning
    MessageBox.Show(msg)
    Return
End If

' Activate add-in with Internet zone security isolation
Dim addInTokens As Collection(Of AddInToken) = AddInStore.FindAddIns(GetType(WPFAddInHostView), appPath)
Dim wpfAddInToken As AddInToken = addInTokens(0)
Me.wpfAddInHostView = wpfAddInToken.Activate(Of WPFAddInHostView)(AddInSecurityLevel.Internet)

' Display add-in UI
Me.addInUIHostGrid.Children.Add(Me.wpfAddInHostView)</code> 
            <para>Die hostanwendung verwendet normalerweise <token>Dnprdnshort</token> Add-In-Modell-Code, um das Add-in zu aktivieren, die implizit die Hostansicht an die hostanwendung zurückgesendet. Die hostanwendung zeigt anschließend die Hostansicht (Dies ist ein <codeEntityReference autoUpgrade="true">System.Windows.Controls.UserControl</codeEntityReference>) aus einer <codeEntityReference autoUpgrade="true">: System.Windows.Controls.Grid</codeEntityReference>.</para> 
            <para>Der Code zum Verarbeiten von Interaktionen mit der Add-in- <token>TLA&#2;Tla_ui</token> in der Anwendungsdomäne ausgeführt wird. Diese Interaktionen umfassen Folgendes:</para>
            <list class="bullet">
              <listItem>
                <para>Behandlung der <codeEntityReference autoUpgrade="true">: System.Windows.Controls.Button</codeEntityReference> <codeEntityReference autoUpgrade="true">e: System.Windows.Controls.Primitives.ButtonBase.Click</codeEntityReference> Ereignis.</para> 
              </listItem> 
              <listItem> 
                <para>Mit der <codeEntityReference autoUpgrade="true">System.Windows.MessageBox</codeEntityReference>.</para> 
              </listItem> 
            </list> 
            <para>Dieser Aktivität ist vollständig von der Host-Anwendung isoliert.</para>
          </content>
        </section>
      </sections>
    </legacy>
  </codeExample>
  <relatedTopics>
\<legacyLink xlink:href="8dd45b02-7218-40f9-857d-40d7b98b850b">Add-Ins und Erweiterbarkeit</legacyLink>
\<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">Übersicht über WPF-Add-Ins</link>
</relatedTopics>
</developerHowToDocument>
