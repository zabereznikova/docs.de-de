---
title: "Benutzerdefinierte zusammengesetzte Designer – Workflowelementpr&#228;sentation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Benutzerdefinierte zusammengesetzte Designer – Workflowelementpr&#228;sentation
<xref:System.Activities.Design.WorkflowItemsPresenter> ist ein Haupttyp im WF\-Designer\-Programmiermodell, der die Bearbeitung einer Auflistung enthaltener Elemente zulässt.In dem Beispiel wird veranschaulicht, wie ein Aktivitätsdesigner erstellt wird, der eine solche bearbeitbare Auflistung aufweist.  
  
 Dieses Beispiel veranschaulicht Folgendes:  
  
-   Erstellen eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Design.WorkflowItemsPresenter>.  
  
-   Erstellen eines Aktivitätsdesigners mit einer "reduzierten" und "erweiterten" Ansicht.  
  
-   Überschreiben eines standardmäßigen Designers in einer neu gehosteten Anwendung.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Öffnen Sie die Beispielprojektmappe **UsingWorkflowItemsPresenter.sln** für C\# oder VB in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.Eine neu gehostete Workflow\-Designer\-Anwendung sollte geöffnet werden, und Sie können Aktivitäten auf den Zeichenbereich ziehen.  
  
## Das Wichtigste zum Beispiel  
 Der Code für dieses Beispiel zeigt Folgendes:  
  
-   Die Aktivität, für die ein Designer erstellt wird: `Parallel`  
  
-   Die Erstellung eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Design.WorkflowItemsPresenter>.Einige wichtige Punkte:  
  
    -   Beachten Sie die Verwendung der WPF\-Datenbindung, um eine Bindung an `ModelItem.Branches` auszuführen.`ModelItem` ist die Eigenschaft im <xref:System.Activities.Design.WorkflowElementDesigner>, die auf das zugrunde liegende Objekt verweist, für das der Designer verwendet wird; in diesem Fall `Parallel`.  
  
    -   <xref:System.Activities.Design.WorkflowItemsPresenter.SpacerTemplate%2A> kann verwendet werden, um ein visuelle Trennung festzulegen, die zwischen den einzelnen Elementen in der Auflistung angezeigt werden soll.  
  
    -   <xref:System.Activities.Design.WorkflowItemsPresenter.ItemsPanel%2A> ist eine Vorlage, die bereitgestellt werden kann, um das Layout der Elemente in der Auflistung zu bestimmen.In diesem Fall wird ein horizontaler Stapelbereich verwendet.  
  
 Dies wird im folgenden Codebeispiel gezeigt.  
  
```xaml  
<sad:WorkflowItemsPresenter HintText="Drop Activities Here"  
                              Items="{Binding Path=ModelItem.Branches}">  
    <sad:WorkflowItemsPresenter.SpacerTemplate>  
      <DataTemplate>  
        <Ellipse Width="10" Height="10" Fill="Black"/>  
      </DataTemplate>  
    </sad:WorkflowItemsPresenter.SpacerTemplate>  
    <sad:WorkflowItemsPresenter.ItemsPanel>  
      <ItemsPanelTemplate>  
        <StackPanel Orientation="Horizontal"/>  
      </ItemsPanelTemplate>  
    </sad:WorkflowItemsPresenter.ItemsPanel>  
  </sad:WorkflowItemsPresenter>  
  
```  
  
-   Führen Sie eine Zuordnung von `DesignerAttribute` zum `Parallel`\-Typ aus, und geben Sie dann die gemeldeten Attribute aus.  
  
    -   Registrieren Sie zuerst alle standardmäßigen Designer.  
  
 Nachfolgend ist das Codebeispiel angegeben.  
  
```csharp  
// register metadata  
(new DesignerMetadata()).Register();  
RegisterCustomMetadata();  
  
```  
  
```vb  
' register metadata  
Dim metadata = New DesignerMetadata()  
metadata.Register()  
' register custom metadata  
RegisterCustomMetadata()  
  
```  
  
-   -   Überschreiben Sie dann "Parallel" in der `RegisterCustomMetadata`\-Methode.  
  
 Im folgenden Code wird dies in C\# und Visual Basic veranschaulicht.  
  
 C\#  
  
```csharp  
void RegisterCustomMetadata()  
{  
      AttributeTableBuilder builder = new AttributeTableBuilder();  
      builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));  
      MetadataStore.AddAttributeTable(builder.CreateTable());  
}  
  
```  
  
```vb  
Sub RegisterCustomMetadata()  
   Dim builder As New AttributeTableBuilder()  
   builder.AddCustomAttributes(GetType(Parallel), New DesignerAttribute(GetType(CustomParallelDesigner)))  
   MetadataStore.AddAttributeTable(builder.CreateTable())  
End Sub  
  
```  
  
-   Beachten Sie schließlich die Verwendung unterschiedlicher Datenvorlagen und Trigger, um die entsprechende Vorlage auf Grundlage der `IsRootDesigner`\-Eigenschaft auszuwählen.  
  
 Nachfolgend ist das Codebeispiel angegeben.  
  
```xaml  
<sad:ActivityDesigner x:Class="Microsoft.Samples.CustomParallelDesigner"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:sad="clr-namespace:System.Activities.Design;assembly=System.Activities.Design"  
    xmlns:sadv="clr-namespace:System.Activities.Design.View;assembly=System.Activities.Design">  
  <sad:ActivityDesigner.Resources>  
    <DataTemplate x:Key="Expanded">  
      <StackPanel>  
        <TextBlock>This is the Expanded View</TextBlock>  
        <sad:WorkflowItemsPresenter HintText="Drop Activities Here"  
                                    Items="{Binding Path=ModelItem.Branches}">  
          <sad:WorkflowItemsPresenter.SpacerTemplate>  
            <DataTemplate>  
              <Ellipse Width="10" Height="10" Fill="Black"/>  
            </DataTemplate>  
          </sad:WorkflowItemsPresenter.SpacerTemplate>  
          <sad:WorkflowItemsPresenter.ItemsPanel>  
            <ItemsPanelTemplate>  
              <StackPanel Orientation="Horizontal"/>  
            </ItemsPanelTemplate>  
          </sad:WorkflowItemsPresenter.ItemsPanel>  
        </sad:WorkflowItemsPresenter>  
      </StackPanel>  
    </DataTemplate>  
    <DataTemplate x:Key="Collapsed">  
      <TextBlock>This is the Collapsed View</TextBlock>  
    </DataTemplate>  
    <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
      <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
      <Style.Triggers>  
        <DataTrigger Binding="{Binding Path=IsRootDesigner}" Value="true">  
          <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
        </DataTrigger>  
      </Style.Triggers>  
    </Style>  
  </sad: ActivityDesigner.Resources>  
  <Grid>  
    <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>  
  </Grid>  
</sad: ActivityDesigner>  
  
```  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`  
  
## Siehe auch  
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>   
 [Entwickeln von Anwendungen mit dem Workflow\-Designer](../Topic/Developing%20Applications%20with%20the%20Workflow%20Designer.md)