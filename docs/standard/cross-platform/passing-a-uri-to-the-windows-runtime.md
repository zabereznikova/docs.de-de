---
title: Übergeben eines URI an die Windows-Runtime
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
ms.openlocfilehash: 71d427c2d602efbd92dc0128b1fada85a987904a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123622"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="39429-102">Übergeben eines URI an die Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="39429-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="39429-103">Windows Runtime-Methoden akzeptieren nur absolute URIs.</span><span class="sxs-lookup"><span data-stu-id="39429-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="39429-104">Wenn Sie einen relativen URI an eine Windows-Runtime Methode übergeben, wird eine <xref:System.ArgumentException> Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="39429-104">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="39429-105">Der Grund: Wenn Sie die Windows-Runtime in .NET Framework Code verwenden, wird die <xref:Windows.Foundation.Uri?displayProperty=nameWithType>-Klasse in IntelliSense als <xref:System.Uri?displayProperty=nameWithType> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39429-105">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="39429-106">Die <xref:System.Uri?displayProperty=nameWithType>-Klasse lässt relative URIs zu, die <xref:Windows.Foundation.Uri?displayProperty=nameWithType>-Klasse jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="39429-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="39429-107">Dies gilt auch für Methoden, die Sie in Windows-Runtime Komponenten verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="39429-107">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="39429-108">Wenn eine Komponente eine Methode verfügbar macht, die einen URI enthält, enthält die Signatur im Code <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39429-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="39429-109">Für Benutzer Ihrer Komponente enthält die Signatur jedoch <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39429-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="39429-110">Ein URI, der an die Komponente übergeben wird, muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="39429-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="39429-111">In diesem Thema wird erläutert, wie Sie einen absoluten URI erkennen und einen solchen erstellen, wenn Sie auf eine Ressource im App-Paket verweisen.</span><span class="sxs-lookup"><span data-stu-id="39429-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="39429-112">Erkennen und Verwenden eines absoluten URIs</span><span class="sxs-lookup"><span data-stu-id="39429-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="39429-113">Verwenden Sie die <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>-Eigenschaft, um sicherzustellen, dass ein URI absolut ist, bevor er an die Windows-Runtime übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="39429-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="39429-114">Das Verwenden dieser Eigenschaft ist effizienter als das Abfangen und Behandeln der <xref:System.ArgumentException>-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="39429-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="39429-115">Verwenden eines absoluten URI für eine Ressource im App-Paket</span><span class="sxs-lookup"><span data-stu-id="39429-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="39429-116">Wenn Sie einen URI für eine Ressource angeben möchten, der im App-Paket enthalten sein soll, können Sie das `ms-appx`-Schema oder `ms-appx-web`-Schema verwenden, um einen absoluten URI zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39429-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="39429-117">Im folgenden Beispiel wird gezeigt, wie Sie die <xref:Windows.UI.Xaml.Controls.WebView.Source%2A>-Eigenschaft für ein <xref:Windows.UI.Xaml.Controls.WebView>-Steuerelement und die <xref:Windows.UI.Xaml.Controls.Image.Source%2A>-Eigenschaft für ein <xref:Windows.UI.Xaml.Controls.Image>-Steuerelement auf Ressourcen, die in einem Ordner mit dem Namen pages enthalten sind, mithilfe von XAML und Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="39429-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="39429-118">Weitere Informationen zu diesen Schemas finden Sie unter [URI-Schemas](/windows/uwp/app-resources/uri-schemes) im Windows dev Center.</span><span class="sxs-lookup"><span data-stu-id="39429-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39429-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39429-119">See also</span></span>

- [<span data-ttu-id="39429-120">.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="39429-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
