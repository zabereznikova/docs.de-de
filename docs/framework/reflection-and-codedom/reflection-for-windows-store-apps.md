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

Beginnend mit dem .NET Framework 4,5 enthält die .NET Framework eine Reihe von reflektionstypen und-Membern für die Verwendung in Windows 8. x Store-Apps. Diese Typen und Member sind im vollständigen .NET Framework sowie im .NET für Windows Store-Apps verfügbar. In diesem Dokument werden die Hauptunterschiede zwischen ihnen und ihren Entsprechungen in .NET Framework 4 und früheren Versionen erklärt.  
  
 Wenn Sie eine Windows 8. x Store-App erstellen, müssen Sie die reflektionstypen und-Member in der [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]verwenden. Diese Typen und Member sind ebenfalls für die Verwendung in Desktop-Apps verfügbar, jedoch nicht erforderlich, sodass Sie denselben Code für beide Typen von Apps verwenden können.  
  
## <a name="typeinfo-and-assembly-loading"></a>TypeInfo und Laden von Assemblys  
 In [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] enthält die <xref:System.Reflection.TypeInfo>-Klasse einen Teil der Funktionen der <xref:System.Type>-Klasse von .NET Framework 4. Ein <xref:System.Type>-Objekt stellt einen Verweis auf eine Typdefinition dar, während ein <xref:System.Reflection.TypeInfo>-Objekt die Typdefinition selbst darstellt. Dadurch können Sie <xref:System.Type>-Objekte ändern, ohne dass die Laufzeit unbedingt die Assembly laden muss, auf die sie verweisen. Das Abrufen des zugeordneten <xref:System.Reflection.TypeInfo>-Objekts erzwingt das Laden der Assembly.  
  
 <xref:System.Reflection.TypeInfo> enthält viele der Member, die in <xref:System.Type> verfügbar sind, und viele der Reflektionseigenschaften in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] geben Auflistungen von <xref:System.Reflection.TypeInfo>-Objekten zurück. Um ein <xref:System.Reflection.TypeInfo>-Objekt aus einem <xref:System.Type>-Objekt abzurufen, verwenden Sie die <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>-Methode.  
  
## <a name="query-methods"></a>Abfragemethoden  
 Verwenden Sie in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] die Reflektionseigenschaften, die <xref:System.Collections.Generic.IEnumerable%601>-Auflistungen zurückgeben, anstelle von Methoden, die Arrays zurückgeben. Reflektionskontexte können einen verzögerten Durchlauf dieser Auflistungen für große Assemblys oder Typen implementieren.  
  
 Die Reflektionseigenschaften geben nur die deklarierten Methoden für ein bestimmtes Objekt wieder. Sie durchlaufen nicht die Vererbungsstruktur. Darüber hinaus verwenden sie keine <xref:System.Reflection.BindingFlags>-Parameter zum Filtern. Stattdessen wird das Filtern im Benutzercode ausgeführt, indem LINQ-Abfragen für die zurückgegebenen Auflistungen verwendet werden. Für Reflektionsobjekte, die mit der Laufzeit ausgelöst werden (z. B. als Ergebnis von `typeof(Object)`), wird das Durchlaufen der Vererbungsstruktur am besten erreicht, indem die Hilfsmethoden der <xref:System.Reflection.RuntimeReflectionExtensions>-Klasse verwendet werden. Consumer von Objekten benutzerdefinierter Reflektionskontexte können diese Methoden nicht verwenden und müssen selbst die Vererbungsstruktur durchlaufen.  
  
## <a name="restrictions"></a>Beschränkungen  
 In einer Windows 8. x Store-App ist der Zugriff auf einige .NET Framework Typen und Member eingeschränkt. Sie können beispielsweise .NET Framework-Methoden, die nicht in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] enthalten sind, nicht mit einem <xref:System.Reflection.MethodInfo>-Objekt aufrufen. Außerdem werden bestimmte Typen und Member, die innerhalb des Kontexts einer Windows 8. x Store-App nicht als sicher eingestuft werden, wie <xref:System.Runtime.InteropServices.Marshal> und <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal> Mitglieder blockiert. Diese Einschränkung betrifft nur .NET Framework-Typen und -Member. Sie können Ihren Code oder Code von Drittanbietern wie gewohnt aufrufen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Reflektionstypen und -member in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] verwendet, um die Methoden und Eigenschaften des <xref:System.Globalization.Calendar>-Typs abzurufen (einschließlich geerbter Methoden und Eigenschaften). Um diesen Code auszuführen, fügen Sie ihn in die Codedatei für eine Windows 8. x-Speicherseite ein, die ein <xref:Windows.UI.Xaml.Controls.TextBlock?displayProperty=nameWithType>-Steuerelement mit dem Namen `textblock1` in einem Projekt namens Reflektion enthält. Wenn Sie diesen Code in einem Projekt mit einem anderen Namen einfügen, müssen Sie darauf achten, dass Sie den Namespacenamen entsprechend Ihrem Projekt ändern.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Reflektion](reflection.md)
