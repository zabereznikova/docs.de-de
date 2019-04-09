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
ms.openlocfilehash: 417af272514ac9ce68c8faa72339f2befc2dd7c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170195"
---
# <a name="handwriting-recognition"></a><span data-ttu-id="ea67e-102">Schrifterkennung</span><span class="sxs-lookup"><span data-stu-id="ea67e-102">Handwriting Recognition</span></span>
<span data-ttu-id="ea67e-103">Dieser Abschnitt beschreibt die Grundlagen der Erkennung in Bezug auf Freihandeingaben in der WPF-Plattform.</span><span class="sxs-lookup"><span data-stu-id="ea67e-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="ea67e-104">Lösungen zu Erkennung</span><span class="sxs-lookup"><span data-stu-id="ea67e-104">Recognition Solutions</span></span>  
 <span data-ttu-id="ea67e-105">Das folgende Beispiel zeigt, wie Sie Freihandeingaben mithilfe der Klasse [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) erkennen.</span><span class="sxs-lookup"><span data-stu-id="ea67e-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea67e-106">Dieses Beispiel erfordert, dass die Handschrifterkennung auf dem System installiert wird.</span><span class="sxs-lookup"><span data-stu-id="ea67e-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="ea67e-107">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Studio mit dem Namen **InkRecognition**.</span><span class="sxs-lookup"><span data-stu-id="ea67e-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="ea67e-108">Ersetzen Sie den Inhalt der Datei „Window1.xaml“ durch den folgenden XAML-Code.</span><span class="sxs-lookup"><span data-stu-id="ea67e-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="ea67e-109">Dieser Code rendert die Benutzeroberfläche der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ea67e-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="ea67e-110">Fügen Sie einen Verweis auf die Microsoft Ink-Assembly „Microsoft.Ink.dll“ hinzu, die unter \Programme\Gemeinsame Dateien\Microsoft Shared\Ink gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea67e-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="ea67e-111">Ersetzen Sie den Inhalt der CodeBehind-Datei durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="ea67e-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ea67e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea67e-112">See also</span></span>

- [<span data-ttu-id="ea67e-113">Microsoft.Ink.InkCollector</span><span class="sxs-lookup"><span data-stu-id="ea67e-113">Microsoft.Ink.InkCollector</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))
