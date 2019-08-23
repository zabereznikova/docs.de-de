---
title: 'Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: aa497194fd4ac65f48773a45175333a1d862b453
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956073"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a>Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente
Sie können Daten einfach in mehreren Formularen gemeinsam nutzen (freigeben), indem Sie die <xref:System.Windows.Forms.BindingSource>-Komponente verwenden. Beispielsweise könnte es sein, dass Sie ein schreibgeschütztes Formular, in dem die Datenquellendaten zusammengefasst werden, sowie ein bearbeitbares Formular anzeigen möchten, das detaillierte Informationen über das Element enthält, das momentan in der Datenquelle ausgewählt ist. In diesem Beispiel wird dieses Szenario veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine <xref:System.Windows.Forms.BindingSource> und die an sie gebundenen Daten in mehreren Formularen gemeinsam genutzt werden können. In diesem Beispiel wird die gemeinsam genutzte <xref:System.Windows.Forms.BindingSource> an den Konstruktor des untergeordneten Formulars übergeben. Das untergeordnete Formular ermöglicht es dem Benutzer, die Daten für das aktuell ausgewählte Element im Hauptformular zu bearbeiten.  
  
> [!NOTE]
> Das <xref:System.Windows.Forms.BindingSource.BindingComplete>-Ereignis für die <xref:System.Windows.Forms.BindingSource>-Komponente wird in diesem Beispiel, um sicherzustellen, dass die beiden Formulare synchronisiert bleiben. Weitere Informationen dazu, warum dies geschieht, finden [Sie unter Vorgehensweise: Stellen Sie sicher, dass mehrere an dieselbe Datenquelle gebundene](../multiple-controls-bound-to-data-source-synchronized.md)Steuerelemente synchronisiert bleiben.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Windows.Forms", "System.Drawing", "System.Data" und "System.Xml".  
  
## <a name="see-also"></a>Siehe auch

- [BindingSource-Komponente](bindingsource-component.md)
- [Windows Forms-Datenbindung](../windows-forms-data-binding.md)
- [Vorgehensweise: Behandeln von Fehlern und Ausnahmen, die beim DataBinding auftreten](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
