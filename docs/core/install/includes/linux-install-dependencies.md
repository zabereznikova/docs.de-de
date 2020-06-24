---
ms.openlocfilehash: b371525c9f4e57c6a09e5bb9232884e5c5e707e0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602765"
---

<span data-ttu-id="712a3-101">Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="712a3-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="712a3-102">Wenn Sie jedoch .NET Core manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:</span><span class="sxs-lookup"><span data-stu-id="712a3-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="712a3-103">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="712a3-103">lttng-ust</span></span>
- <span data-ttu-id="712a3-104">libcurl</span><span class="sxs-lookup"><span data-stu-id="712a3-104">libcurl</span></span>
- <span data-ttu-id="712a3-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="712a3-105">openssl-libs</span></span>
- <span data-ttu-id="712a3-106">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="712a3-106">krb5-libs</span></span>
- <span data-ttu-id="712a3-107">libicu</span><span class="sxs-lookup"><span data-stu-id="712a3-107">libicu</span></span>
- <span data-ttu-id="712a3-108">zlib</span><span class="sxs-lookup"><span data-stu-id="712a3-108">zlib</span></span>
- <span data-ttu-id="712a3-109">libunwind</span><span class="sxs-lookup"><span data-stu-id="712a3-109">libunwind</span></span>
- <span data-ttu-id="712a3-110">libuuid</span><span class="sxs-lookup"><span data-stu-id="712a3-110">libuuid</span></span>

<span data-ttu-id="712a3-111">Wenn die OpenSSL-Version der Zielruntime-Umgebung 1.1 oder neuer ist, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="712a3-111">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="712a3-112">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="712a3-112">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="712a3-113">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="712a3-113">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="712a3-114">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="712a3-114">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="712a3-115">Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="712a3-115">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="712a3-116">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="712a3-116">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>
