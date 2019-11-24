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
ms.openlocfilehash: 9aaec282fda0a038d14f3a0cd57e1a8a2855f2ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448132"
---
# <a name="reflection-in-the-net-framework-for-windows-store-apps"></a>Reflektion in .NET Framework für Windows Store-Apps

Starting with the .NET Framework 4.5, the .NET Framework includes a set of reflection types and members for use in Windows 8.x Store apps. These types and members are available in the full .NET Framework as well as in the .NET for Windows Store apps. In diesem Dokument werden die Hauptunterschiede zwischen ihnen und ihren Entsprechungen in .NET Framework 4 und früheren Versionen erklärt.  
  
 If you are creating a Windows 8.x Store app, you must use the reflection types and members in the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]. Diese Typen und Member sind ebenfalls für die Verwendung in Desktop-Apps verfügbar, jedoch nicht erforderlich, sodass Sie denselben Code für beide Typen von Apps verwenden können.  
  
## <a name="typeinfo-and-assembly-loading"></a>TypeInfo und Laden von Assemblys  
 In [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] enthält die <xref:System.Reflection.TypeInfo>-Klasse einen Teil der Funktionen der <xref:System.Type>-Klasse von .NET Framework 4. Ein <xref:System.Type>-Objekt stellt einen Verweis auf eine Typdefinition dar, während ein <xref:System.Reflection.TypeInfo>-Objekt die Typdefinition selbst darstellt. Dadurch können Sie <xref:System.Type>-Objekte ändern, ohne dass die Laufzeit unbedingt die Assembly laden muss, auf die sie verweisen. Das Abrufen des zugeordneten <xref:System.Reflection.TypeInfo>-Objekts erzwingt das Laden der Assembly.  
  
 <xref:System.Reflection.TypeInfo> enthält viele der Member, die in <xref:System.Type> verfügbar sind, und viele der Reflektionseigenschaften in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] geben Auflistungen von <xref:System.Reflection.TypeInfo>-Objekten zurück. Um ein <xref:System.Reflection.TypeInfo>-Objekt aus einem <xref:System.Type>-Objekt abzurufen, verwenden Sie die <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>-Methode.  
  
## <a name="query-methods"></a>Abfragemethoden  
 Verwenden Sie in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] die Reflektionseigenschaften, die <xref:System.Collections.Generic.IEnumerable%601>-Auflistungen zurückgeben, anstelle von Methoden, die Arrays zurückgeben. Reflektionskontexte können einen verzögerten Durchlauf dieser Auflistungen für große Assemblys oder Typen implementieren.  
  
 Die Reflektionseigenschaften geben nur die deklarierten Methoden für ein bestimmtes Objekt wieder. Sie durchlaufen nicht die Vererbungsstruktur. Darüber hinaus verwenden sie keine <xref:System.Reflection.BindingFlags>-Parameter zum Filtern. Stattdessen wird das Filtern im Benutzercode ausgeführt, indem LINQ-Abfragen für die zurückgegebenen Auflistungen verwendet werden. Für Reflektionsobjekte, die mit der Laufzeit ausgelöst werden (z. B. als Ergebnis von `typeof(Object)`), wird das Durchlaufen der Vererbungsstruktur am besten erreicht, indem die Hilfsmethoden der <xref:System.Reflection.RuntimeReflectionExtensions>-Klasse verwendet werden. Consumer von Objekten benutzerdefinierter Reflektionskontexte können diese Methoden nicht verwenden und müssen selbst die Vererbungsstruktur durchlaufen.  
  
## <a name="restrictions"></a>Beschränkungen  
 In a Windows 8.x Store app, access to some .NET Framework types and members is restricted. Sie können beispielsweise .NET Framework-Methoden, die nicht in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] enthalten sind, nicht mit einem <xref:System.Reflection.MethodInfo>-Objekt aufrufen. In addition, certain types and members that are not considered safe within the context of a Windows 8.x Store app are blocked, as are <xref:System.Runtime.InteropServices.Marshal> and <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal> members. Diese Einschränkung betrifft nur .NET Framework-Typen und -Member. Sie können Ihren Code oder Code von Drittanbietern wie gewohnt aufrufen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Reflektionstypen und -member in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] verwendet, um die Methoden und Eigenschaften des <xref:System.Globalization.Calendar>-Typs abzurufen (einschließlich geerbter Methoden und Eigenschaften). To run this code, paste it into the code file for a Windows 8.x Store page that contains a <xref:Windows.UI.Xaml.Controls.TextBlock?displayProperty=nameWithType> control named `textblock1` in a project named Reflection. Wenn Sie diesen Code in einem Projekt mit einem anderen Namen einfügen, müssen Sie darauf achten, dass Sie den Namespacenamen entsprechend Ihrem Projekt ändern.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Reflektion](reflection.md)
