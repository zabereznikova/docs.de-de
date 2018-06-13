---
title: Verwenden eines benutzerdefinierten Ausdrucks-Editors
ms.date: 03/30/2017
ms.assetid: 0901b58b-e037-44a8-8281-f6f54361cfca
ms.openlocfilehash: 4eb39fbd51cf4f1914f7fdca545f9c9fd8e83240
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518576"
---
# <a name="using-a-custom-expression-editor"></a><span data-ttu-id="73a25-102">Verwenden eines benutzerdefinierten Ausdrucks-Editors</span><span class="sxs-lookup"><span data-stu-id="73a25-102">Using a Custom Expression Editor</span></span>
<span data-ttu-id="73a25-103">Ein benutzerdefinierter Ausdrucks-Editor kann implementiert werden, um eine umfangreichere oder einfachere Ausdrucksbearbeitung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="73a25-103">A custom expression editor can be implemented to provide a richer or simpler expression editing experience.</span></span> <span data-ttu-id="73a25-104">Es gibt mehrere Szenarios, in denen ein benutzerdefinierter Ausdrucks-Editor nützlich ist:</span><span class="sxs-lookup"><span data-stu-id="73a25-104">There are several scenarios in which you might want to use a custom expression editor:</span></span>  
  
-   <span data-ttu-id="73a25-105">Zur Unterstützung von IntelliSense und anderen umfangreichen Bearbeitungsfunktionen in einem neu gehosteten Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="73a25-105">To provide support for IntelliSense and other rich editing features in a rehosted workflow designer.</span></span> <span data-ttu-id="73a25-106">Diese Funktionalität muss bereitgestellt werden, da der standardmäßige Visual Studio-Ausdrucks-Editor im neu gehosteten Anwendungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="73a25-106">This functionality must be provided because the default Visual Studio expression editor cannot be used in rehosted applications.</span></span>  
  
-   <span data-ttu-id="73a25-107">Vereinfachen Sie den Ausdruck Ihnen Bearbeitungsfunktionen für Wirtschaftsanalysten, sodass sie nicht, z. B. beim Erlernen von Visual Basic oder Visual Basic-Ausdrücke behandeln benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="73a25-107">To simplify the expression editing experience for the business analyst users, so that they are not, for example, required to learn Visual Basic or deal with Visual Basic expressions.</span></span>  
  
 <span data-ttu-id="73a25-108">Zur Implementierung eines benutzerdefinierten Ausdrucks-Editors sind drei einfache Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="73a25-108">Three basic steps are needed to implement a custom expression editor:</span></span>  
  
1.  <span data-ttu-id="73a25-109">Implementieren Sie die <xref:System.Activities.Presentation.View.IExpressionEditorService>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="73a25-109">Implement the <xref:System.Activities.Presentation.View.IExpressionEditorService> interface.</span></span> <span data-ttu-id="73a25-110">Über diese Schnittstelle wird die Erstellung und Löschung von Ausdrucks-Editoren verwaltet.</span><span class="sxs-lookup"><span data-stu-id="73a25-110">This interface manages the creation and destruction of expression editors.</span></span>  
  
2.  <span data-ttu-id="73a25-111">Implementieren Sie die <xref:System.Activities.Presentation.View.IExpressionEditorInstance>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="73a25-111">Implement the <xref:System.Activities.Presentation.View.IExpressionEditorInstance> interface.</span></span> <span data-ttu-id="73a25-112">Über diese Schnittstelle wird die Benutzeroberfläche zur Ausdrucksbearbeitung implementiert.</span><span class="sxs-lookup"><span data-stu-id="73a25-112">This interface implements the UI for expression editing UI.</span></span>  
  
3.  <span data-ttu-id="73a25-113">Veröffentlichen des <xref:System.Activities.Presentation.View.IExpressionEditorService> in der neu gehosteten Workflowanwendung.</span><span class="sxs-lookup"><span data-stu-id="73a25-113">Publish the <xref:System.Activities.Presentation.View.IExpressionEditorService> in your rehosted workflow application.</span></span>  
  
## <a name="implementing-a-custom-expression-editor-in-a-class-library"></a><span data-ttu-id="73a25-114">Implementieren eines benutzerdefinierten Ausdrucks-Editors in einer Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="73a25-114">Implementing a Custom Expression Editor in a Class Library</span></span>  
 <span data-ttu-id="73a25-115">Es folgt ein Codebeispiel für eine `MyEditorService`-Klasse (Machbarkeitsstudie) zur Implementierung der <xref:System.Activities.Presentation.View.IExpressionEditorService>-Schnittstelle, die in einem MyExpressionEditorService-Bibliotheksprojekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="73a25-115">Here is a sample of code for a (proof of concept) `MyEditorService` class that implements the <xref:System.Activities.Presentation.View.IExpressionEditorService> interface is contained in a MyExpressionEditorService library project.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Activities.Presentation.View;  
using System.Activities.Presentation.Hosting;  
using System.Activities.Presentation.Model;  
  
namespace MyExpressionEditorService  
{  
    public class MyEditorService : IExpressionEditorService  
    {  
        public void CloseExpressionEditors()  
        {  
  
        }  
        public IExpressionEditorInstance CreateExpressionEditor(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces, List<ModelItem> variables, string text)  
        {  
            MyExpressionEditorInstance instance = new MyExpressionEditorInstance();  
            return instance;  
        }  
        public IExpressionEditorInstance CreateExpressionEditor(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces, List<ModelItem> variables, string text, System.Windows.Size initialSize)  
                {  
            MyExpressionEditorInstance instance = new MyExpressionEditorInstance();  
            return instance;  
        }  
        public IExpressionEditorInstance CreateExpressionEditor(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces, List<ModelItem> variables, string text, Type expressionType)  
            {  
            MyExpressionEditorInstance instance = new MyExpressionEditorInstance();  
            return instance;  
        }  
        public IExpressionEditorInstance CreateExpressionEditor(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces, List<ModelItem> variables, string text, Type expressionType, System.Windows.Size initialSize)  
        {  
            MyExpressionEditorInstance instance = new MyExpressionEditorInstance();  
            return instance;  
        }  
        public void UpdateContext(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces)  
        {  
  
        }  
  
    }  
}  
```  
  
 <span data-ttu-id="73a25-116">Im Folgenden finden Sie den Code für eine `MyExpressionEditorInstance`-Klasse zur Implementierung der <xref:System.Activities.Presentation.View.IExpressionEditorInstance>-Schnittstelle, die in einem MyExpressionEditorService-Bibliotheksprojekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="73a25-116">Here is the code for a `MyExpressionEditorInstance` class that implements the <xref:System.Activities.Presentation.View.IExpressionEditorInstance> interface in a MyExpressionEditorService library project.</span></span>  
  
```  
using System;  
using System.Activities.Presentation.View;  
using System.Windows;  
using System.Reflection;  
using System.Windows.Controls;  
  
namespace MyExpressionEditorService  
{  
    public class MyExpressionEditorInstance : IExpressionEditorInstance  
    {  
        private TextBox textBox = new TextBox();  
  
        public bool AcceptsReturn { get; set; }  
        public bool AcceptsTab { get; set; }  
        public bool HasAggregateFocus {  
            get  
            {  
                return true;  
            }  
        }  
  
        public System.Windows.Controls.ScrollBarVisibility HorizontalScrollBarVisibility { get; set; }  
        public System.Windows.Controls.Control HostControl {  
            get  
            {  
                return textBox;  
            }  
        }  
        public int MaxLines { get; set; }  
        public int MinLines { get; set; }  
        public string Text { get; set; }  
        public System.Windows.Controls.ScrollBarVisibility VerticalScrollBarVisibility { get; set; }  
  
        public event EventHandler Closing;  
        public event EventHandler GotAggregateFocus;  
        public event EventHandler LostAggregateFocus;  
        public event EventHandler TextChanged;  
  
        public bool CanCompleteWord()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanCopy()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanCut()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanDecreaseFilterLevel()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanGlobalIntellisense()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanIncreaseFilterLevel()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanParameterInfo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanPaste()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanQuickInfo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanRedo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanUndo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
  
        public void ClearSelection()  
        {  
            MessageBox.Show(MethodBase.GetCurrentMethod().Name);  
        }  
        public void Close()  
        {  
            MessageBox.Show(MethodBase.GetCurrentMethod().Name);  
        }  
        public bool CompleteWord()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Copy()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Cut()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool DecreaseFilterLevel()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public void Focus()  
        {  
            MessageBox.Show(MethodBase.GetCurrentMethod().Name);  
        }  
        public string GetCommittedText()  
        {  
            return "CommittedText";  
        }  
        public bool GlobalIntellisense()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool IncreaseFilterLevel()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool ParameterInfo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Paste()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool QuickInfo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Redo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Undo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
    }  
}  
```  
  
### <a name="publishing-a-custom-expression-editor-in-a-wpf-project"></a><span data-ttu-id="73a25-117">Veröffentlichen eines benutzerdefinierten Ausdrucks-Editors in einem WPF-Projekt</span><span class="sxs-lookup"><span data-stu-id="73a25-117">Publishing a Custom Expression Editor in a WPF Project</span></span>  
 <span data-ttu-id="73a25-118">Dieser Code zeigt, wie der Designer in einer [!INCLUDE[avalon2](../../../includes/avalon2-md.md)]-Anwendung neu gehostet wird und wie der `MyEditorService`-Dienst erstellt und veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="73a25-118">Here is the code that shows how to rehost the designer in a [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] application and how to create and publish the `MyEditorService` service.</span></span> <span data-ttu-id="73a25-119">Vor der Verwendung dieses Codes fügen Sie von dem Projekt aus, das die Anwendung avalon2 enthält, einen Verweis auf das MyExpressionEditorService-Bibliotheksprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="73a25-119">Before using this code, add a reference to the MyExpressionEditorService library project from the project that contains the avalon2 application.</span></span>  
  
```  
using System.Windows;  
using System.Windows.Controls;  
using System.Activities.Presentation;  
using System.Activities.Statements;  
using System.Activities.Core.Presentation;  
using System.Activities.Presentation.View;  
using MyExpressionEditorService;  
  
namespace WpfApplication1  
{  
    /// <summary>  
    /// Interaction logic for MainWindow.xaml  
    /// </summary>  
    public partial class MainWindow : Window  
    {  
  
        private MyEditorService expressionEditorService;  
        public MainWindow()  
        {  
            InitializeComponent();  
            new DesignerMetadata().Register();  
            createDesigner();  
        }  
  
        public void createDesigner()  
        {  
            WorkflowDesigner designer = new WorkflowDesigner();  
            Sequence root = new Sequence()  
            {  
                Activities = {  
                new Assign(),  
                new WriteLine()}  
            };  
  
            designer.Load(root);  
  
            Grid.SetColumn(designer.View, 0);  
  
            // Create ExpressionEditorService   
            this.expressionEditorService = new MyEditorService();  
  
            // Publish the instance of MyEditorService.  
            designer.Context.Services.Publish<IExpressionEditorService>(this.expressionEditorService);  
  
            MyGrid.Children.Add(designer.View);  
        }  
    }  
}  
```  
  
### <a name="notes"></a><span data-ttu-id="73a25-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73a25-120">Notes</span></span>  
 <span data-ttu-id="73a25-121">Bei Verwendung einer **ExpressionTextBox** Steuerelement in einem benutzerdefinierten Aktivitätsdesigner ist es nicht erforderlich, erstellen und Zerstören von Ausdrucks-Editoren mithilfe der <xref:System.Activities.Presentation.View.IExpressionEditorService.CreateExpressionEditor%2A> und <xref:System.Activities.Presentation.View.IExpressionEditorService.CloseExpressionEditors%2A> Methoden die <xref:System.Activities.Presentation.View.IExpressionEditorService> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="73a25-121">If you are using an **ExpressionTextBox** control in a custom activity designer, it is not necessary to create and destroy expression editors using the <xref:System.Activities.Presentation.View.IExpressionEditorService.CreateExpressionEditor%2A> and <xref:System.Activities.Presentation.View.IExpressionEditorService.CloseExpressionEditors%2A> methods of the <xref:System.Activities.Presentation.View.IExpressionEditorService> interface.</span></span> <span data-ttu-id="73a25-122">Die <xref:System.Activities.Presentation.View.ExpressionTextBox>-Klasse übernimmt dies für Sie.</span><span class="sxs-lookup"><span data-stu-id="73a25-122">The <xref:System.Activities.Presentation.View.ExpressionTextBox> class manages this for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a25-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73a25-123">See Also</span></span>  
 <xref:System.Activities.Presentation.View.IExpressionEditorService>  
 <xref:System.Activities.Presentation.View.IExpressionEditorInstance>  
 [<span data-ttu-id="73a25-124">Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="73a25-124">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
