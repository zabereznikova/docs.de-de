---
title: 'Gewusst wie: Verwenden von Ressourcen in lokalisierbaren Anwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212474"
---
# <a name="how-to-use-resources-in-localizable-apps"></a>Gewusst wie: Verwenden von Ressourcen in lokalisierbaren apps

Lokalisierung bedeutet, dass eine Benutzeroberfläche an verschiedene Kulturen angepasst wird. Zu diesem Zweck müssen Text wie Titel, Beschriftungen und Listenfeld Elemente übersetzt werden. Um die Übersetzung zu vereinfachen, werden die zu über setzenden Elemente in Ressourcen Dateien gesammelt. Informationen zum Erstellen einer Ressourcen Datei für die Lokalisierung finden Sie unter [Lokalisieren einer APP](how-to-localize-an-application.md) . Um eine WPF-Anwendung lokalisierbar zu machen, müssen Entwickler alle lokalisierbaren Ressourcen in einer Ressourcenassembly erstellen. Die Ressourcenassembly wird in verschiedene Sprachen lokalisiert, und der Code Behind verwendet die Ressourcenverwaltungs-API zum Laden.

## <a name="example"></a>Beispiel

Eine der erforderlichen Dateien für eine WPF-Anwendung ist eine Projektdatei (. proj). Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein. Dies wird im folgenden XAML-Beispiel veranschaulicht.

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

Um eine Ressource in Ihrer Anwendung zu verwenden, instanziieren <xref:System.Resources.ResourceManager> und laden Sie die gewünschte Ressource. Dies wird im folgenden c#-Code veranschaulicht.

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a>Siehe auch

- [Lokalisieren einer APP](how-to-localize-an-application.md)
