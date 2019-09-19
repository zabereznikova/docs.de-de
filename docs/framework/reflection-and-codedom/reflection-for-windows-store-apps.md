---
title: Reflektion in .NET Framework für Windows Store-Apps
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection, Windows Store apps
- .NET for Windows Store apps, TypeInfo class
ms.assetid: 0d07090c-9b47-4ecc-81d1-29d539603c9b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9edab859900bf2001956045a5285801bb61d310
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045939"
---
# <a name="reflection-in-the-net-framework-for-windows-store-apps"></a>Reflektion in .NET Framework für Windows Store-Apps
Ab .NET Framework 4.5 stellt .NET Framework eine Reihe von Reflektionstypen und -membern für [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps zur Verfügung. Diese Typen und Member sind im vollständigen .NET Framework sowie im [.NET für Windows Store-Apps](https://go.microsoft.com/fwlink/?LinkID=225700) verfügbar. In diesem Dokument werden die Hauptunterschiede zwischen ihnen und ihren Entsprechungen in .NET Framework 4 und früheren Versionen erklärt.  
  
 Wenn Sie eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App erstellen, müssen Sie die Reflektionstypen und -member im [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] verwenden. Diese Typen und Member sind ebenfalls für die Verwendung in Desktop-Apps verfügbar, jedoch nicht erforderlich, sodass Sie denselben Code für beide Typen von Apps verwenden können.  
  
## <a name="typeinfo-and-assembly-loading"></a>TypeInfo und Laden von Assemblys  
 In [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] enthält die <xref:System.Reflection.TypeInfo>-Klasse einen Teil der Funktionen der <xref:System.Type>-Klasse von .NET Framework 4. Ein <xref:System.Type>-Objekt stellt einen Verweis auf eine Typdefinition dar, während ein <xref:System.Reflection.TypeInfo>-Objekt die Typdefinition selbst darstellt. Dadurch können Sie <xref:System.Type>-Objekte ändern, ohne dass die Laufzeit unbedingt die Assembly laden muss, auf die sie verweisen. Das Abrufen des zugeordneten <xref:System.Reflection.TypeInfo>-Objekts erzwingt das Laden der Assembly.  
  
 <xref:System.Reflection.TypeInfo> enthält viele der Member, die in <xref:System.Type> verfügbar sind, und viele der Reflektionseigenschaften in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] geben Auflistungen von <xref:System.Reflection.TypeInfo>-Objekten zurück. Um ein <xref:System.Reflection.TypeInfo>-Objekt aus einem <xref:System.Type>-Objekt abzurufen, verwenden Sie die <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>-Methode.  
  
## <a name="query-methods"></a>Abfragemethoden  
 Verwenden Sie in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] die Reflektionseigenschaften, die <xref:System.Collections.Generic.IEnumerable%601>-Auflistungen zurückgeben, anstelle von Methoden, die Arrays zurückgeben. Reflektionskontexte können einen verzögerten Durchlauf dieser Auflistungen für große Assemblys oder Typen implementieren.  
  
 Die Reflektionseigenschaften geben nur die deklarierten Methoden für ein bestimmtes Objekt wieder. Sie durchlaufen nicht die Vererbungsstruktur. Darüber hinaus verwenden sie keine <xref:System.Reflection.BindingFlags>-Parameter zum Filtern. Stattdessen wird das Filtern im Benutzercode ausgeführt, indem LINQ-Abfragen für die zurückgegebenen Auflistungen verwendet werden. Für Reflektionsobjekte, die mit der Laufzeit ausgelöst werden (z. B. als Ergebnis von `typeof(Object)`), wird das Durchlaufen der Vererbungsstruktur am besten erreicht, indem die Hilfsmethoden der <xref:System.Reflection.RuntimeReflectionExtensions>-Klasse verwendet werden. Consumer von Objekten benutzerdefinierter Reflektionskontexte können diese Methoden nicht verwenden und müssen selbst die Vererbungsstruktur durchlaufen.  
  
## <a name="restrictions"></a>Beschränkungen  
 In einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App wird der Zugriff auf einige .NET Framework-Typen und -Member eingeschränkt. Sie können beispielsweise .NET Framework-Methoden, die nicht in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] enthalten sind, nicht mit einem <xref:System.Reflection.MethodInfo>-Objekt aufrufen. Darüber hinaus werden bestimmte Typen und Member, die innerhalb einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App als nicht sicher eingestuft werden, sowie <xref:System.Runtime.InteropServices.Marshal>-Member und <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal>-Member blockiert. Diese Einschränkung betrifft nur .NET Framework-Typen und -Member. Sie können Ihren Code oder Code von Drittanbietern wie gewohnt aufrufen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Reflektionstypen und -member in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] verwendet, um die Methoden und Eigenschaften des <xref:System.Globalization.Calendar>-Typs abzurufen (einschließlich geerbter Methoden und Eigenschaften). Um diesen Code auszuführen, fügen Sie ihn in eine Codedatei für eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Seite ein, die ein Steuerelement <xref:Windows.UI.Xaml.Controls.TextBlock?displayProperty=nameWithType> mit dem Namen `textblock1` in einem Projekt mit dem Namen „Reflektion“ enthält. Wenn Sie diesen Code in einem Projekt mit einem anderen Namen einfügen, müssen Sie darauf achten, dass Sie den Namespacenamen entsprechend Ihrem Projekt ändern.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Reflexion](reflection.md)
- [.NET für Windows Store-Apps – unterstützte APIs](https://go.microsoft.com/fwlink/?LinkID=225700)
