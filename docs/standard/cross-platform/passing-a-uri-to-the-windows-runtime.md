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
# <a name="passing-a-uri-to-the-windows-runtime"></a>Übergeben eines URI an die Windows-Runtime
Windows Runtime-Methoden akzeptieren nur absolute URIs. Wenn Sie einen relativen URI an eine Windows-Runtime Methode übergeben, wird eine <xref:System.ArgumentException> Ausnahme ausgelöst. Der Grund: Wenn Sie die Windows-Runtime in .NET Framework Code verwenden, wird die <xref:Windows.Foundation.Uri?displayProperty=nameWithType>-Klasse in IntelliSense als <xref:System.Uri?displayProperty=nameWithType> angezeigt. Die <xref:System.Uri?displayProperty=nameWithType>-Klasse lässt relative URIs zu, die <xref:Windows.Foundation.Uri?displayProperty=nameWithType>-Klasse jedoch nicht. Dies gilt auch für Methoden, die Sie in Windows-Runtime Komponenten verfügbar machen. Wenn eine Komponente eine Methode verfügbar macht, die einen URI enthält, enthält die Signatur im Code <xref:System.Uri?displayProperty=nameWithType>. Für Benutzer Ihrer Komponente enthält die Signatur jedoch <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. Ein URI, der an die Komponente übergeben wird, muss ein absoluter URI sein.  
  
In diesem Thema wird erläutert, wie Sie einen absoluten URI erkennen und einen solchen erstellen, wenn Sie auf eine Ressource im App-Paket verweisen.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Erkennen und Verwenden eines absoluten URIs  
Verwenden Sie die <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>-Eigenschaft, um sicherzustellen, dass ein URI absolut ist, bevor er an die Windows-Runtime übergeben wird. Das Verwenden dieser Eigenschaft ist effizienter als das Abfangen und Behandeln der <xref:System.ArgumentException>-Ausnahme.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Verwenden eines absoluten URI für eine Ressource im App-Paket  
Wenn Sie einen URI für eine Ressource angeben möchten, der im App-Paket enthalten sein soll, können Sie das `ms-appx`-Schema oder `ms-appx-web`-Schema verwenden, um einen absoluten URI zu erstellen.  
  
Im folgenden Beispiel wird gezeigt, wie Sie die <xref:Windows.UI.Xaml.Controls.WebView.Source%2A>-Eigenschaft für ein <xref:Windows.UI.Xaml.Controls.WebView>-Steuerelement und die <xref:Windows.UI.Xaml.Controls.Image.Source%2A>-Eigenschaft für ein <xref:Windows.UI.Xaml.Controls.Image>-Steuerelement auf Ressourcen, die in einem Ordner mit dem Namen pages enthalten sind, mithilfe von XAML und Code festlegen.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Weitere Informationen zu diesen Schemas finden Sie unter [URI-Schemas](/windows/uwp/app-resources/uri-schemes) im Windows dev Center.  
  
## <a name="see-also"></a>Weitere Informationen

- [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
