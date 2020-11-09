---
title: Winmdexp.exe-Fehlermeldungen
description: Hier erfahren Sie Grundlegendes zu Winmdexp.exe-Fehlermeldungen (Exporttool für Metadaten der Windows-Runtime), die nur während des Buildprozesses angezeigt werden, wenn die .NET-Kompilierung erfolgreich ist.
ms.date: 03/30/2017
f1_keywords:
- WME1095
- WME1110
- WME15
- WME1094
- WME1078
- WME1080
- WME1014
- WME1025
- WME1089
- WME1111
- WME1010
- WME1013
- WME1055
- WME1005
- WME1033
- WME1003
- WME1011
- WME1046
- WME0013
- WME1032
- WME1029
- WME1048
- WME1019
- WME1106
- WME0012
- WME1017
- WME1098
- WME1039
- WME20
- WME1006
- WME1088
- WME0004
- WME10
- WME12
- WME0015
- WME0017
- WME1026
- WME1045
- WME1002
- WME1051
- WME1107
- WME1100
- WME1072
- WME1090
- WME1105
- WME1022
- WME11
- WME17
- WME1063
- WME1041
- WME1057
- WME1037
- WME1007
- WME3
- WME1096
- WME0003
- WME0006
- WME1065
- WME1102
- WME1070
- WME1113
- WME1064
- WME1061
- WME1066
- WME1018
- WME1049
- WME1027
- WME1101
- WME1058
- WME0005
- WME1083
- WME1004
- WME1073
- WME1087
- WME1077
- WME19
- WME1086
- WME1085
- WME1040
- WME8
- WME1081
- WME1023
- WME4
- WME1050
- WME7
- WME1091
- WME14
- WME0007
- WME1024
- WME1012
- WME1036
- WME0010
- WME1104
- WME1035
- WME1021
- WME1075
- WME5
- WME13
- WME1074
- WME1028
- WME0014
- WME1030
- WME1008
- WME1052
- WME1079
- WME1054
- WME1093
- WME1042
- WME2
- WME1062
- WME6
- WME1001
- WME0011
- WME16
- WME0001
- WME1020
- WME1084
- WME1103
- WME1092
- WME1
- WME0002
- WME1112
- WME1016
- WME1060
- WME0008
- WME0016
- WME1097
- WME1034
- WME1108
- WME1082
- WME1099
- WME1069
- WME1031
- WME1009
- WME1068
- WME1067
- WME1059
- WME18
- WME1038
- WME0009
- WME1109
- WME1056
- WME1076
- WME1071
- WME1044
- WME1043
- WME1053
- WME1015
- WME1047
- WME9
helpviewer_keywords:
- Winmdexp.exe, error messages
- Windows Runtime Metadata Export Tool, error messages
- error messages, Winmdexp.exe
ms.assetid: 8271973c-deba-47a6-8e5e-04ce63f146ad
ms.openlocfilehash: 69a3cc8e9c32a3981de2c978011a140602a501ed
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400773"
---
# <a name="winmdexpexe-error-messages"></a><span data-ttu-id="a066d-103">Winmdexp.exe-Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="a066d-103">Winmdexp.exe error messages</span></span>

<span data-ttu-id="a066d-104">Der Buildprozess ruft [Winmdexp.exe (Windows-Runtime-Metadaten-Exporttool)](winmdexp-exe-windows-runtime-metadata-export-tool.md) auf, wenn Sie die Vorlage **Komponente für Windows-Runtime** in Visual Studio 2012 verwenden, sodass Winmdexp.exe-Fehlermeldungen in der **Fehlerliste** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a066d-104">The build process calls [Winmdexp.exe (Windows Runtime Metadata Export Tool)](winmdexp-exe-windows-runtime-metadata-export-tool.md) when you use the **Windows Runtime Component** template in Visual Studio 2012, so Winmdexp.exe error messages appear in the **Error List**.</span></span> <span data-ttu-id="a066d-105">Winmdexp.exe arbeitet auf einem Modul, das mit der `/target:winmdobj`-Option kompiliert ist.</span><span class="sxs-lookup"><span data-stu-id="a066d-105">Winmdexp.exe operates on a module that is compiled with the `/target:winmdobj` option.</span></span> <span data-ttu-id="a066d-106">Da ein kompiliertes Modul als Eingabe erforderlich ist, erscheinen die Fehlermeldungen nicht, bis die Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a066d-106">Because it requires a compiled module as input, its error messages don't appear unless compilation succeeds.</span></span>

<span data-ttu-id="a066d-107">Die Fehlermeldungen sollen alle Informationen enthalten, die Sie benötigen, um die Fehlerbedingungen anzugehen, die gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="a066d-107">The error messages are designed to contain all the information you need to address the error conditions they report.</span></span> <span data-ttu-id="a066d-108">Jedoch erfordern einige Probleme mehr Informationen als in die Meldung passen.</span><span class="sxs-lookup"><span data-stu-id="a066d-108">However, some problems require more information than will fit in the message.</span></span> <span data-ttu-id="a066d-109">Zusätzliche Informationen finden Sie unter [Diagnostizieren von Fehlerbedingungen für Komponenten für Windows-Runtime](/previous-versions/hh977010(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="a066d-109">You can find additional information in [Diagnosing Windows Runtime component error conditions](/previous-versions/hh977010(v=vs.110)).</span></span>

<span data-ttu-id="a066d-110">Falls Ihr Fehler nicht in diesem Artikel behandelt wird, und Sie der Meinung sind, dass die Meldung nicht genügend Informationen enthält, um das Problem zu beheben, verwenden Sie den Link für Feedback in diesem Artikel, und fügen Sie die Fehlermeldung ein.</span><span class="sxs-lookup"><span data-stu-id="a066d-110">If your error is not discussed in that article, and you feel that the message doesn't contain sufficient information to address the issue, use the feedback link in that article and include the error message.</span></span> <span data-ttu-id="a066d-111">Oder melden Sie den Fehler auf der [Website der Entwicklercommunity](https://aka.ms/feedback/report?space=61).</span><span class="sxs-lookup"><span data-stu-id="a066d-111">Alternatively, you can file a bug at the [Developer Community website](https://aka.ms/feedback/report?space=61).</span></span> <span data-ttu-id="a066d-112">Sie können in den [Microsoft-Foren](https://social.msdn.microsoft.com/Forums/) auch nach weiteren Informationen suchen.</span><span class="sxs-lookup"><span data-stu-id="a066d-112">You can also look for more information on the [Microsoft Forums](https://social.msdn.microsoft.com/Forums/).</span></span>

## <a name="see-also"></a><span data-ttu-id="a066d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a066d-113">See also</span></span>

- [<span data-ttu-id="a066d-114">Winmdexp.exe (Windows-Runtime-Metadaten-Exporttool)</span><span class="sxs-lookup"><span data-stu-id="a066d-114">Winmdexp.exe (Windows Runtime Metadata Export Tool)</span></span>](winmdexp-exe-windows-runtime-metadata-export-tool.md)
- <span data-ttu-id="a066d-115">[Diagnostizieren von Fehlerbedingungen der Windows-Runtime-Komponente](/previous-versions/hh977010(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="a066d-115">[Diagnosing Windows Runtime component error conditions](/previous-versions/hh977010(v=vs.110))</span></span>
