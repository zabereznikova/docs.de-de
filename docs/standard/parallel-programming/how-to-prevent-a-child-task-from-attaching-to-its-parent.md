---
title: "Gewusst wie: Verhindern des Anfügens einer untergeordneten Aufgabe an die übergeordnete Aufgabe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4717e3a077648d9db51fe39228209617b384bd0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>Gewusst wie: Verhindern des Anfügens einer untergeordneten Aufgabe an die übergeordnete Aufgabe
Dieses Dokument veranschaulicht, wie eine untergeordnete Aufgabe nicht an die übergeordnete Aufgabe angefügt werden soll. Verhindern, dass eine untergeordnete Aufgabe mit seinem übergeordneten Element verbindet eignet sich, beim Aufrufen einer Komponente, die von einem Drittanbieter geschrieben und verwendet, die auch Aufgaben. Z. B. eine Drittanbieter-Komponente, verwendet der <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> Option zum Erstellen einer <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> -Objekt kann Probleme im Code verursachen, wenn sie lang andauernde oder löst einen Ausnahmefehler aus.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Auswirkungen der Verwendung der Standardoptionen der Auswirkungen der verhindert, dass einer untergeordnete Aufgabe an das übergeordnete Element anfügt. Das Beispiel erstellt eine <xref:System.Threading.Tasks.Task> -Objekt, das in einer Bibliothek eines Drittanbieters aufruft, die auch verwendet eine <xref:System.Threading.Tasks.Task> Objekt. Die Bibliothek eines Drittanbieters verwendet die <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> Option zum Erstellen der <xref:System.Threading.Tasks.Task> Objekt. Die Anwendung verwendet die <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> Option aus, um die übergeordnete Aufgabe zu erstellen. Diese Option weist die Laufzeit So entfernen Sie die <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> Spezifikation in untergeordneten Aufgaben.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Da eine übergeordnete Aufgabe nicht beendet wird, ehe alle untergeordneten Aufgaben abgeschlossen sind, kann eine lang andauernde untergeordnete Aufgabe dazu führen, dass die gesamte Anwendung schlecht ausgeführt. In diesem Beispiel wenn die Anwendung die Standardoptionen verwendet, um die übergeordnete Aufgabe zu erstellen muss die untergeordnete Aufgabe beendet, bevor die übergeordnete Aufgabe abgeschlossen ist. Wenn die Anwendung mithilfe der <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> Option, das untergeordnete Element ist nicht an der übergeordneten Tabelle angefügt. Aus diesem Grund kann die Anwendung zusätzliche Aufgaben ausführen, nachdem die übergeordnete Aufgabe abgeschlossen ist, und vor dem Beenden der untergeordneten Aufgabe warten muss.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `DenyChildAttach.cs` (`DenyChildAttach.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe DenyChildAttach.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe DenyChildAttach.vb**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
## <a name="see-also"></a>Siehe auch  
 [Aufgabenbasierte asynchrone Programmierung](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
