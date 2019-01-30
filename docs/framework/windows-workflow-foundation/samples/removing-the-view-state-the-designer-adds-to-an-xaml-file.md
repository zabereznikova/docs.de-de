---
title: Entfernen der Designer ansichtzustands in einer XAML-Datei – WF
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: 71a2aadeefd53b391f4589ed9dc32d9cd6e3183a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260566"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a>Entfernen des dem Designer hinzugefügt, dass ein XAML-Datei

Dieses Beispiel veranschaulicht, wie eine Klasse erstellt wird, die von <xref:System.Xaml.XamlWriter> abgeleitet wird, und entfernt den Ansichtszustand aus einer XAML-Datei. [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] schreibt Informationen in das XAML-Dokument, das als Ansichtszustand bezeichnet wird. Der Ansichtszustand bezieht sich auf die Informationen, die während der Entwurfszeit erforderlich sind, z. B. die Layoutpositionierung, jedoch nicht zur Laufzeit. [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] fügt diese Informationen in das XAML-Dokument ein, während es bearbeitet wird. [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] schreibt den Ansichtszustand in der XAML-Datei mit dem `mc:Ignorable`-Attribut. Daher werden diese Informationen nicht geladen, wenn die Laufzeit die XAML-Datei lädt. In diesem Beispiel wird veranschaulicht, wie eine Klasse erstellt wird, mit der diese Ansichtszustandsinformationen bei der Verarbeitung von XAML-Knoten entfernt werden.

## <a name="discussion"></a>Diskussion

In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Writer erstellt wird.

Zum Erstellen eines benutzerdefinierten XAML-Writers müssen Sie eine Klasse erstellen, die von <xref:System.Xaml.XamlWriter> erbt. Wie XAML-Writer häufig geschachtelt werden, ist es üblich, zu verfolgen einen "inneren" XAML-Writer. Diese "inneren" Writer können als Verweis auf den verbleibenden Stapel XAML-Writer, sodass Sie über mehrere Einstiegspunkte verfügen und die Verarbeitung der restlichen Stapels delegieren betrachtet werden.

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

1. Öffnen Sie mit Visual Studio 2010 die ViewStateCleaningWriter.sln-Projektmappendatei.

2. Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zu dem Verzeichnis, in dem ViewStageCleaningWriter.exe erstellt wird.

3. Führen Sie ViewStateCleaningWriter.exe für die Datei Workflow1.xaml aus.

   Die Syntax für die ausführbare Datei ist im folgenden Beispiel dargestellt.

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   Hierdurch erfolgt die Ausgabe einer XAML-Datei, die \[Ausgabedatei], der alle Ansichtszustandsinformationen entfernt wurde.

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
> Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`