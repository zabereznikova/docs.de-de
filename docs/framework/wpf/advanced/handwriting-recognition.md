---
title: Schrifterkennung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
ms.openlocfilehash: d72d8b42a23205d8599b23a467677dd2f05d5cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542375"
---
# <a name="handwriting-recognition"></a><span data-ttu-id="7f8f7-102">Schrifterkennung</span><span class="sxs-lookup"><span data-stu-id="7f8f7-102">Handwriting Recognition</span></span>
<span data-ttu-id="7f8f7-103">Dieser Abschnitt beschreibt die Grundlagen der Erkennung in Bezug auf Freihandeingaben in der WPF-Plattform.</span><span class="sxs-lookup"><span data-stu-id="7f8f7-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="7f8f7-104">Lösungen zu Erkennung</span><span class="sxs-lookup"><span data-stu-id="7f8f7-104">Recognition Solutions</span></span>  
 <span data-ttu-id="7f8f7-105">Das folgende Beispiel zeigt, wie Sie Freihandeingaben mithilfe der Klasse [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) erkennen.</span><span class="sxs-lookup"><span data-stu-id="7f8f7-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f8f7-106">Dieses Beispiel erfordert, dass die Handschrifterkennung auf dem System installiert wird.</span><span class="sxs-lookup"><span data-stu-id="7f8f7-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="7f8f7-107">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Studio mit dem Namen **InkRecognition**.</span><span class="sxs-lookup"><span data-stu-id="7f8f7-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="7f8f7-108">Ersetzen Sie den Inhalt der Datei „Window1.xaml“ durch den folgenden XAML-Code.</span><span class="sxs-lookup"><span data-stu-id="7f8f7-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="7f8f7-109">Dieser Code rendert die Benutzeroberfläche der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7f8f7-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="7f8f7-110">Fügen Sie einen Verweis auf die Microsoft Ink-Assembly „Microsoft.Ink.dll“ hinzu, die unter \Programme\Gemeinsame Dateien\Microsoft Shared\Ink gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="7f8f7-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="7f8f7-111">Ersetzen Sie den Inhalt der CodeBehind-Datei durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="7f8f7-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7f8f7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f8f7-112">See Also</span></span>  
 <span data-ttu-id="7f8f7-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7f8f7-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span></span>
