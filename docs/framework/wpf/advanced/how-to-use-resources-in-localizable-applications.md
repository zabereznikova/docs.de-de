---
title: 'Vorgehensweise: Verwenden von Ressourcen in lokalisierbaren Anwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 3634bb72cbacfb02b0a1230a47a1664cb8ce5009
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238461"
---
# <a name="how-to-use-resources-in-localizable-applications"></a>Vorgehensweise: Verwenden von Ressourcen in lokalisierbaren Anwendungen
Lokalisierung bezeichnet die Anpassung einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für andere Kulturen. Dazu müssen Text (z.B. Titel), Beschriftungen, Listenfeldelemente usw. übersetzt werden. Damit die Übersetzung vereinfacht wird, werden die zu übersetzten Elemente in Ressourcendateien gesammelt. Finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md) für Informationen zum Erstellen einer Ressourcendatei für die Lokalisierung. Zu einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung lokalisierbar sein, müssen Entwickler alle lokalisierbaren Ressourcen in einer Ressourcenassembly erstellen. Die Ressourcenassembly wird in verschiedenen Sprachen lokalisiert, und das Code-Behind verwendet Ressourcenverwaltungs-API zum Laden. Einer der erforderlichen Dateien für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ist eine Projektdatei (.proj). Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein. Dies wird im folgenden Codebeispiel gezeigt.  
  
## <a name="example"></a>Beispiel  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Um eine Ressource in Ihrer Anwendung verwenden zu können, instanziieren Sie <xref:System.Resources.ResourceManager> und Laden Sie die Ressource, die Sie verwenden möchten. Im folgenden Beispiel wird die hierfür erforderliche Vorgehensweise veranschaulicht:  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
