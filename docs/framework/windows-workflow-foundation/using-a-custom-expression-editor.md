---
title: Verwenden eines benutzerdefinierten Ausdrucks-Editors
ms.date: 03/30/2017
ms.assetid: 0901b58b-e037-44a8-8281-f6f54361cfca
ms.openlocfilehash: e33e804d73239794a7f9cf9f3c28c3808f8b963e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293311"
---
# <a name="using-a-custom-expression-editor"></a><span data-ttu-id="2b5cd-102">Verwenden eines benutzerdefinierten Ausdrucks-Editors</span><span class="sxs-lookup"><span data-stu-id="2b5cd-102">Using a Custom Expression Editor</span></span>

<span data-ttu-id="2b5cd-103">Ein benutzerdefinierter Ausdrucks-Editor kann implementiert werden, um eine umfangreichere oder einfachere Ausdrucksbearbeitung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-103">A custom expression editor can be implemented to provide a richer or simpler expression editing experience.</span></span> <span data-ttu-id="2b5cd-104">Es gibt mehrere Szenarios, in denen ein benutzerdefinierter Ausdrucks-Editor nützlich ist:</span><span class="sxs-lookup"><span data-stu-id="2b5cd-104">There are several scenarios in which you might want to use a custom expression editor:</span></span>  
  
- <span data-ttu-id="2b5cd-105">Zur Unterstützung von IntelliSense und anderen umfangreichen Bearbeitungsfunktionen in einem neu gehosteten Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-105">To provide support for IntelliSense and other rich editing features in a rehosted workflow designer.</span></span> <span data-ttu-id="2b5cd-106">Diese Funktion muss bereitgestellt werden, da der standardmäßige Visual Studio-Ausdrucks-Editor nicht in neu gehosteten Anwendungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-106">This functionality must be provided because the default Visual Studio expression editor cannot be used in rehosted applications.</span></span>  
  
- <span data-ttu-id="2b5cd-107">Um das Verhalten der Ausdrucks Bearbeitung für die Benutzer des Wirtschafts Analytikers zu vereinfachen, sodass diese nicht zum Beispiel erforderlich sind, um Visual Basic zu erlernen oder mit Visual Basic Ausdrücken umzugehen.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-107">To simplify the expression editing experience for the business analyst users, so that they are not, for example, required to learn Visual Basic or deal with Visual Basic expressions.</span></span>  
  
 <span data-ttu-id="2b5cd-108">Zur Implementierung eines benutzerdefinierten Ausdrucks-Editors sind drei einfache Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="2b5cd-108">Three basic steps are needed to implement a custom expression editor:</span></span>  
  
1. <span data-ttu-id="2b5cd-109">Implementieren Sie die <xref:System.Activities.Presentation.View.IExpressionEditorService>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-109">Implement the <xref:System.Activities.Presentation.View.IExpressionEditorService> interface.</span></span> <span data-ttu-id="2b5cd-110">Über diese Schnittstelle wird die Erstellung und Löschung von Ausdrucks-Editoren verwaltet.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-110">This interface manages the creation and destruction of expression editors.</span></span>  
  
2. <span data-ttu-id="2b5cd-111">Implementieren Sie die <xref:System.Activities.Presentation.View.IExpressionEditorInstance>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-111">Implement the <xref:System.Activities.Presentation.View.IExpressionEditorInstance> interface.</span></span> <span data-ttu-id="2b5cd-112">Über diese Schnittstelle wird die Benutzeroberfläche zur Ausdrucksbearbeitung implementiert.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-112">This interface implements the UI for expression editing UI.</span></span>  
  
3. <span data-ttu-id="2b5cd-113">Veröffentlichen des <xref:System.Activities.Presentation.View.IExpressionEditorService> in der neu gehosteten Workflowanwendung.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-113">Publish the <xref:System.Activities.Presentation.View.IExpressionEditorService> in your rehosted workflow application.</span></span>  
  
## <a name="implementing-a-custom-expression-editor-in-a-class-library"></a><span data-ttu-id="2b5cd-114">Implementieren eines benutzerdefinierten Ausdrucks-Editors in einer Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="2b5cd-114">Implementing a Custom Expression Editor in a Class Library</span></span>  

 <span data-ttu-id="2b5cd-115">Es folgt ein Codebeispiel für eine `MyEditorService`-Klasse (Machbarkeitsstudie) zur Implementierung der <xref:System.Activities.Presentation.View.IExpressionEditorService>-Schnittstelle, die in einem MyExpressionEditorService-Bibliotheksprojekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-115">Here is a sample of code for a (proof of concept) `MyEditorService` class that implements the <xref:System.Activities.Presentation.View.IExpressionEditorService> interface is contained in a MyExpressionEditorService library project.</span></span>  
  
```csharp  
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
  
 <span data-ttu-id="2b5cd-116">Im Folgenden finden Sie den Code für eine `MyExpressionEditorInstance`-Klasse zur Implementierung der <xref:System.Activities.Presentation.View.IExpressionEditorInstance>-Schnittstelle, die in einem MyExpressionEditorService-Bibliotheksprojekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-116">Here is the code for a `MyExpressionEditorInstance` class that implements the <xref:System.Activities.Presentation.View.IExpressionEditorInstance> interface in a MyExpressionEditorService library project.</span></span>  
  
```csharp  
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
  
### <a name="publishing-a-custom-expression-editor-in-a-wpf-project"></a><span data-ttu-id="2b5cd-117">Veröffentlichen eines benutzerdefinierten Ausdrucks-Editors in einem WPF-Projekt</span><span class="sxs-lookup"><span data-stu-id="2b5cd-117">Publishing a Custom Expression Editor in a WPF Project</span></span>  

 <span data-ttu-id="2b5cd-118">Der folgende Code zeigt, wie der Designer in einer WPF-Anwendung neu gehostet wird und wie der Dienst erstellt und veröffentlicht wird `MyEditorService` .</span><span class="sxs-lookup"><span data-stu-id="2b5cd-118">Here is the code that shows how to rehost the designer in a WPF application and how to create and publish the `MyEditorService` service.</span></span> <span data-ttu-id="2b5cd-119">Vor der Verwendung dieses Codes fügen Sie von dem Projekt aus, das die Anwendung avalon2 enthält, einen Verweis auf das MyExpressionEditorService-Bibliotheksprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-119">Before using this code, add a reference to the MyExpressionEditorService library project from the project that contains the avalon2 application.</span></span>  
  
```csharp  
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
  
### <a name="notes"></a><span data-ttu-id="2b5cd-120">Notizen</span><span class="sxs-lookup"><span data-stu-id="2b5cd-120">Notes</span></span>  

 <span data-ttu-id="2b5cd-121">Wenn Sie in einem benutzerdefinierten Aktivitäts Designer ein **ExpressionTextBox** -Steuerelement verwenden, ist es nicht erforderlich, Ausdrucks-Editoren mithilfe der <xref:System.Activities.Presentation.View.IExpressionEditorService.CreateExpressionEditor%2A> -Methode und der- <xref:System.Activities.Presentation.View.IExpressionEditorService.CloseExpressionEditors%2A> Methode der-Schnittstelle zu erstellen und zu zerstören <xref:System.Activities.Presentation.View.IExpressionEditorService> .</span><span class="sxs-lookup"><span data-stu-id="2b5cd-121">If you are using an **ExpressionTextBox** control in a custom activity designer, it is not necessary to create and destroy expression editors using the <xref:System.Activities.Presentation.View.IExpressionEditorService.CreateExpressionEditor%2A> and <xref:System.Activities.Presentation.View.IExpressionEditorService.CloseExpressionEditors%2A> methods of the <xref:System.Activities.Presentation.View.IExpressionEditorService> interface.</span></span> <span data-ttu-id="2b5cd-122">Die <xref:System.Activities.Presentation.View.ExpressionTextBox>-Klasse übernimmt dies für Sie.</span><span class="sxs-lookup"><span data-stu-id="2b5cd-122">The <xref:System.Activities.Presentation.View.ExpressionTextBox> class manages this for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b5cd-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b5cd-123">See also</span></span>

- <xref:System.Activities.Presentation.View.IExpressionEditorService>
- <xref:System.Activities.Presentation.View.IExpressionEditorInstance>
- [<span data-ttu-id="2b5cd-124">Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="2b5cd-124">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
