---
title: 'Entfernen des Ansichts Zustands, der vom Designer zu einer XAML-Datei hinzugefügt wird: WF'
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: f431275140e821aa5ec4d2235322f06be87d5ee2
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715611"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a>Entfernen des Ansichts Zustands, der vom Designer zu einer XAML-Datei hinzugefügt wird

Dieses Beispiel veranschaulicht, wie eine Klasse erstellt wird, die von <xref:System.Xaml.XamlWriter> abgeleitet wird, und entfernt den Ansichtszustand aus einer XAML-Datei. Windows Workflow-Designer schreibt Informationen in das XAML-Dokument, das als Ansichts Zustand bezeichnet wird. Der Ansichtszustand bezieht sich auf die Informationen, die während der Entwurfszeit erforderlich sind, z. B. die Layoutpositionierung, jedoch nicht zur Laufzeit. Workflow-Designer fügt diese Informationen in das XAML-Dokument ein, während es bearbeitet wird. Workflow-Designer schreibt den Ansichts Zustand in die XAML-Datei mit dem Attribut `mc:Ignorable`, sodass diese Informationen nicht geladen werden, wenn die Laufzeit die XAML-Datei lädt. In diesem Beispiel wird veranschaulicht, wie eine Klasse erstellt wird, mit der diese Ansichtszustandsinformationen bei der Verarbeitung von XAML-Knoten entfernt werden.

## <a name="discussion"></a>Diskussion

In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Writer erstellt wird.

Zum Erstellen eines benutzerdefinierten XAML-Writers müssen Sie eine Klasse erstellen, die von <xref:System.Xaml.XamlWriter> erbt. Da XAML-Writer oft geschachtelt sind, ist es üblich, einen "inneren" XAML-Writer nachzuverfolgen. Diese "inneren" Writer können als Verweis auf den verbleibenden Stapel von XAML-Writern angesehen werden, sodass mehrere Einstiegspunkte funktionieren und die Verarbeitung dann an den Rest des Stapels delegiert werden kann.

In diesem Beispiel gibt es einige relevante Elemente. Eines ist die Überprüfung, ob das geschriebene Element aus einem Designernamespace stammt. Beachten Sie, dass dies die Verwendung anderer Typen des Designernamespace in einem Workflow nicht mehr ermöglicht.

```csharp
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)
{
    return xamlMember.IsAttachable &&
        xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);
}

const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";

// The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.
public ViewStateCleaningWriter(XamlWriter innerWriter)
{
    this.InnerWriter = innerWriter;
    this.MemberStack = new Stack<XamlMember>();
}

XamlWriter InnerWriter {get; set; }
Stack<XamlMember> MemberStack {get; set; }
```

Hierdurch wird auch ein Stapel von XAML-Membern erstellt, die beim Durchlaufen des Knotenstreams verwendet werden. Die verbleibende Arbeit dieses Beispiels ist zum größten Teil in der `WriteStartMember`-Methode enthalten.

```csharp
public override void WriteStartMember(XamlMember xamlMember)
{
    MemberStack.Push(xamlMember);

    if (IsDesignerAttachedProperty(xamlMember))
    {
        m_attachedPropertyDepth++;
    }

    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteStartMember(xamlMember);
}
```

Nachfolgende Methoden können überprüfen, ob sie immer noch in einem Ansichtszustandscontainer enthalten sind. Wenn dies der Fall ist, können sie zurückkehren und den Knoten nicht im Writerstapel weiter übergeben.

```csharp
public override void WriteValue(Object value)
{
    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteValue(value);
}
```

Um einen benutzerdefinierten XAML-Writer verwenden zu können, müssen Sie ihn in einem Stapel XAML-Writer verketten. Der folgende Code zeigt diese Verwendung.

```csharp
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);
```

## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie mit Visual Studio 2010 die Projektmappendatei "viewstatuecleaningwriter. sln".

2. Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zu dem Verzeichnis, in dem ViewStageCleaningWriter.exe erstellt wird.

3. Führen Sie ViewStateCleaningWriter.exe für die Datei Workflow1.xaml aus.

   Die Syntax für die ausführbare Datei ist im folgenden Beispiel dargestellt.

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   Dadurch wird eine XAML-Datei an \[Ausgabedatei] ausgegeben, die alle Ansichts Zustandsinformationen entfernt hat.

> [!NOTE]
> Für einen <xref:System.Activities.Statements.Sequence>-Workflow wird eine Reihe von Virtualisierungshinweisen entfernt. Dies veranlasst den Designer, das Layout beim nächsten Laden neu zu berechnen. Wenn Sie dieses Beispiel für ein <xref:System.Activities.Statements.Flowchart> verwenden, werden alle Positionierungs- und Zeilenroutinginformationen entfernt. Bei nachfolgendem Laden in den Designer werden alle Aktivitäten auf der linken Seite des Bildschirms gestapelt.

## <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a>So erstellen Sie eine Beispiel-XAML-Datei zur Verwendung mit diesem Beispiel

1. Öffnen Sie Visual Studio 2010.

2. So erstellen Sie eine neue Workflowkonsolenanwendung.

3. Legen Sie einige Aktivitäten in der Entwurfsfläche ab.

4. Speichern Sie die Workflow-XAML-Datei.

5. Überprüfen Sie die XAML-Datei auf die Eigenschaften, die dem Ansichtszustand zugeordnet sind.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`
