---
title: 'Gewusst wie: Hinzufügen benutzerdefinierter Informationen zu einem TreeView- oder ListView-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: faed586a5814526b0169ea46c8bb452e3777d8ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182424"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a><span data-ttu-id="04057-102">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="04057-102">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>
<span data-ttu-id="04057-103">Sie können einen abgeleiteten Knoten <xref:System.Windows.Forms.TreeView> in einem Windows <xref:System.Windows.Forms.ListView> Forms-Steuerelement oder ein abgeleitetes Element in einem Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="04057-103">You can create a derived node in a Windows Forms <xref:System.Windows.Forms.TreeView> control or a derived item in a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="04057-104">Durch Ableitung können Sie jegliche Felder, die Sie benötigen, sowie die benutzerdefinierten Methoden und Konstruktoren für deren Behandlung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="04057-104">Derivation allows you to add any fields you require, as well as custom methods and constructors for handling them.</span></span> <span data-ttu-id="04057-105">Eine Verwendung dieser Funktion ist das Anfügen eines Customer-Objekts an jeden Strukturknoten oder jedes Listenelement.</span><span class="sxs-lookup"><span data-stu-id="04057-105">One use of this feature is to attach a Customer object to each tree node or list item.</span></span> <span data-ttu-id="04057-106">Die Beispiele hier <xref:System.Windows.Forms.TreeView> sind für ein Steuerelement, aber <xref:System.Windows.Forms.ListView> der gleiche Ansatz kann für ein Steuerelement verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04057-106">The examples here are for a <xref:System.Windows.Forms.TreeView> control, but the same approach can be used for a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
### <a name="to-derive-a-tree-node"></a><span data-ttu-id="04057-107">So leiten Sie einen Strukturknoten ab</span><span class="sxs-lookup"><span data-stu-id="04057-107">To derive a tree node</span></span>  
  
- <span data-ttu-id="04057-108">Erstellen Sie eine neue Knotenklasse, die von der <xref:System.Windows.Forms.TreeNode> Klasse abgeleitet ist und über ein benutzerdefiniertes Feld zum Aufzeichnen eines Dateipfads verfügt.</span><span class="sxs-lookup"><span data-stu-id="04057-108">Create a new node class, derived from the <xref:System.Windows.Forms.TreeNode> class, which has a custom field to record a file path.</span></span>  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a><span data-ttu-id="04057-109">So verwenden Sie einen abgeleiteten Strukturknoten</span><span class="sxs-lookup"><span data-stu-id="04057-109">To use a derived tree node</span></span>  
  
1. <span data-ttu-id="04057-110">Sie können den neuen abgeleiteten Strukturknoten als Parameter für Funktionsaufrufe verwenden.</span><span class="sxs-lookup"><span data-stu-id="04057-110">You can use the new derived tree node as a parameter to function calls.</span></span>  
  
     <span data-ttu-id="04057-111">Im folgenden Beispiel ist der Pfad für den Speicherort der Textdatei der Ordner „Eigene Dateien“.</span><span class="sxs-lookup"><span data-stu-id="04057-111">In the example below, the path set for the location of the text file is the My Documents folder.</span></span> <span data-ttu-id="04057-112">Dies geschieht, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Betriebssystem Windows ausgeführt wird, über dieses Verzeichnis verfügen.</span><span class="sxs-lookup"><span data-stu-id="04057-112">This is done because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="04057-113">Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="04057-113">This also allows users with minimal system access levels to safely run the application.</span></span>  
  
    ```vb  
    ' You should replace the bold text file
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2. <span data-ttu-id="04057-114">Wenn Sie den Strukturknoten übergeben und als <xref:System.Windows.Forms.TreeNode> Klasse eingegeben werden, müssen Sie in die abgeleitete Klasse umsetzen.</span><span class="sxs-lookup"><span data-stu-id="04057-114">If you are passed the tree node and it is typed as a <xref:System.Windows.Forms.TreeNode> class, then you will need to cast to your derived class.</span></span> <span data-ttu-id="04057-115">Die Umwandlung ist eine explizite Konvertierung von einem Objekt in ein anderes.</span><span class="sxs-lookup"><span data-stu-id="04057-115">Casting is an explicit conversion from one type of object to another.</span></span> <span data-ttu-id="04057-116">Weitere Informationen zum Umgießen finden Sie unter [Implizite und Explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [Umwandlungs- und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md) (Visual C) oder [Cast-Operator: ()](/cpp/cpp/cast-operator-parens) (Visual C++).</span><span class="sxs-lookup"><span data-stu-id="04057-116">For more information on casting, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [Casting and type conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) (Visual C#), or [Cast Operator: ()](/cpp/cpp/cast-operator-parens) (Visual C++).</span></span>  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="04057-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04057-117">See also</span></span>

- [<span data-ttu-id="04057-118">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="04057-118">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="04057-119">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="04057-119">ListView Control</span></span>](listview-control-windows-forms.md)
