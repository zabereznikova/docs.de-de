---
title: Binden von Steuerelementen an DBNull-Daten Bankwerte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: 175d7f5aee2540916480e2c55a485af1f9d16653
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746662"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a><span data-ttu-id="7e681-102">Gewusst wie: Binden von Windows Forms-Steuerelementen an DBNull-Datenbankwerte</span><span class="sxs-lookup"><span data-stu-id="7e681-102">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>
<span data-ttu-id="7e681-103">Wenn Sie Windows Forms-Steuerelemente an eine Datenquelle gebunden haben und die Datenquelle einen <xref:System.DBNull>-Wert zurückgibt, können Sie einen entsprechenden Wert ersetzen, ohne Ereignisse behandeln, formatieren oder analysieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7e681-103">When you bind Windows Forms controls to a data source and the data source returns a <xref:System.DBNull> value, you can substitute an appropriate value without handling, formatting, or parsing events.</span></span> <span data-ttu-id="7e681-104">Die <xref:System.Windows.Forms.Binding.NullValue%2A>-Eigenschaft konvertiert <xref:System.DBNull> beim Formatieren oder Analysieren der Datenquellenwerte in ein angegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="7e681-104">The <xref:System.Windows.Forms.Binding.NullValue%2A> property will convert <xref:System.DBNull> to a specified object when formatting or parsing the data source values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e681-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e681-105">Example</span></span>  
 <span data-ttu-id="7e681-106">Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.DBNull>-Wert in zwei verschiedenen Situationen gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="7e681-106">The following example demonstrates how to bind a <xref:System.DBNull> value in two different situations.</span></span> <span data-ttu-id="7e681-107">In der ersten Situation wird dargestellt, wie <xref:System.Windows.Forms.Binding.NullValue%2A> für eine Zeichenfolgeneigenschaft festgelegt wird, und in der zweiten Situation wird dargestellt, wie <xref:System.Windows.Forms.Binding.NullValue%2A> für eine Bildeigenschaft festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="7e681-107">The first demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for a string property; the second demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for an image property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 <span data-ttu-id="7e681-108">Der Typ der gebundenen Eigenschaft muss mit dem Typ der <xref:System.Windows.Forms.Binding.NullValue%2A>-Eigenschaft übereinstimmen. Andernfalls wird ein Fehler ausgegeben, und es werden keine weiteren <xref:System.Windows.Forms.Binding.NullValue%2A>-Werte verarbeitet .</span><span class="sxs-lookup"><span data-stu-id="7e681-108">The types of the bound property and the <xref:System.Windows.Forms.Binding.NullValue%2A> property must be the same or an error will result, and no further <xref:System.Windows.Forms.Binding.NullValue%2A> values will be processed.</span></span> <span data-ttu-id="7e681-109">In diesem Fall wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7e681-109">In this situation, an exception will not be thrown.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7e681-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7e681-110">Compiling the Code</span></span>  
 <span data-ttu-id="7e681-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7e681-111">This example requires:</span></span>  
  
- <span data-ttu-id="7e681-112">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="7e681-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e681-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e681-113">See also</span></span>

- [<span data-ttu-id="7e681-114">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="7e681-114">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="7e681-115">Vorgehensweise: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="7e681-115">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
- [<span data-ttu-id="7e681-116">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="7e681-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
