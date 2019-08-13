---
title: 创建基于微服务的复合 UI
description: 微服务体系结构不仅针对后端。 了解微服务在前端中的使用。
ms.date: 09/20/2018
ms.openlocfilehash: 0d1825d6183b79a0e10f70fc6cfee6ca79a837d8
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817830"
---
# <a name="creating-composite-ui-based-on-microservices"></a><span data-ttu-id="0a62c-104">创建基于微服务的复合 UI</span><span class="sxs-lookup"><span data-stu-id="0a62c-104">Creating composite UI based on microservices</span></span>

<span data-ttu-id="0a62c-105">微服务体系结构通常从服务器端处理数据和逻辑开始。</span><span class="sxs-lookup"><span data-stu-id="0a62c-105">Microservices architecture often starts with the server-side handling data and logic.</span></span> <span data-ttu-id="0a62c-106">但是，根据微服务设计应用程序 UI 是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="0a62c-106">However, a more advanced approach is to design your application UI based on microservices as well.</span></span> <span data-ttu-id="0a62c-107">这意味着拥有的是由微服务生成的复合 UI，而不是服务器上的微服务和使用微服务的整体式客户端应用。</span><span class="sxs-lookup"><span data-stu-id="0a62c-107">That means having a composite UI produced by the microservices, instead of having microservices on the server and just a monolithic client app consuming the microservices.</span></span> <span data-ttu-id="0a62c-108">按照这种方法构建的微服务具有逻辑和可视化表示形式，功能十分完整。</span><span class="sxs-lookup"><span data-stu-id="0a62c-108">With this approach, the microservices you build can be complete with both logic and visual representation.</span></span>

<span data-ttu-id="0a62c-109">图 4-20 显示了在整体式客户端应用程序中使用微服务的更为简单的方式。</span><span class="sxs-lookup"><span data-stu-id="0a62c-109">Figure 4-20 shows the simpler approach of just consuming microservices from a monolithic client application.</span></span> <span data-ttu-id="0a62c-110">当然，在生成 HTML 之后，可以创建一个 ASP.NET MVC 服务，再生成 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="0a62c-110">Of course, you could have an ASP.NET MVC service in between producing the HTML and JavaScript.</span></span> <span data-ttu-id="0a62c-111">该图是一张简图，强调拥有使用微服务的单一（整体式）客户端 UI，该 UI 仅关注逻辑和数据，而不关注 UI 形状（HTML 和 JavaScript）。</span><span class="sxs-lookup"><span data-stu-id="0a62c-111">The figure is a simplification that highlights that you have a single (monolithic) client UI consuming the microservices, which just focus on logic and data and not on the UI shape (HTML and JavaScript).</span></span>

![连接到各项微服务的整体式 UI 应用程序。](./media/image20.png)

<span data-ttu-id="0a62c-113">图 4-20  。</span><span class="sxs-lookup"><span data-stu-id="0a62c-113">**Figure 4-20**.</span></span> <span data-ttu-id="0a62c-114">使用后端微服务的整体式 UI 应用程序</span><span class="sxs-lookup"><span data-stu-id="0a62c-114">A monolithic UI application consuming back-end microservices</span></span>

<span data-ttu-id="0a62c-115">与之相比，复合 UI 是由微服务本身精确生成和组合成的。</span><span class="sxs-lookup"><span data-stu-id="0a62c-115">In contrast, a composite UI is precisely generated and composed by the microservices themselves.</span></span> <span data-ttu-id="0a62c-116">一些微服务可控制 UI 特定区域的视觉形状。</span><span class="sxs-lookup"><span data-stu-id="0a62c-116">Some of the microservices drive the visual shape of specific areas of the UI.</span></span> <span data-ttu-id="0a62c-117">主要区别在于，这具有基于模板的客户端 UI 组件（例如 TypeScript 类），而这些模板的数据构形 UI ViewModel 来自于各个微服务。</span><span class="sxs-lookup"><span data-stu-id="0a62c-117">The key difference is that you have client UI components (TypeScript classes, for example) based on templates, and the data-shaping-UI ViewModel for those templates comes from each microservice.</span></span>

<span data-ttu-id="0a62c-118">客户端应用程序启动时，每个客户端 UI 组件（例如 TypeScript 类）自身都会注册一个基础结构微服务，该微服务能够为特定方案提供 ViewModel。</span><span class="sxs-lookup"><span data-stu-id="0a62c-118">At client application start-up time, each of the client UI components (TypeScript classes, for example) registers itself with an infrastructure microservice capable of providing ViewModels for a given scenario.</span></span> <span data-ttu-id="0a62c-119">如果微服务形状发生更改，则 UI 也会更改。</span><span class="sxs-lookup"><span data-stu-id="0a62c-119">If the microservice changes the shape, the UI changes also.</span></span>

<span data-ttu-id="0a62c-120">图 4-21 显示了一种复合 UI 方法。</span><span class="sxs-lookup"><span data-stu-id="0a62c-120">Figure 4-21 shows a version of this composite UI approach.</span></span> <span data-ttu-id="0a62c-121">这只是一个简化示例，因为可能还有其他微服务，它们将聚合基于不同技术的精细部件。</span><span class="sxs-lookup"><span data-stu-id="0a62c-121">This is simplified because you might have other microservices that are aggregating granular parts that are based on different techniques.</span></span> <span data-ttu-id="0a62c-122">具体取决于构建的是传统 Web 方法 (ASP.NET MVC) 还是 SPA （单页应用程序）。</span><span class="sxs-lookup"><span data-stu-id="0a62c-122">It depends on whether you're building a traditional web approach (ASP.NET MVC) or an SPA (Single Page Application).</span></span>

![在复合 UI 应用程序中，每个 UI 区域都由一个 UI 复合微服务生成，其作用类似于迷你网关。](./media/image21.png)

<span data-ttu-id="0a62c-124">图 4-21  。</span><span class="sxs-lookup"><span data-stu-id="0a62c-124">**Figure 4-21**.</span></span> <span data-ttu-id="0a62c-125">由后端微服务形成的复合 UI 应用程序示例</span><span class="sxs-lookup"><span data-stu-id="0a62c-125">Example of a composite UI application shaped by back-end microservices</span></span>

<span data-ttu-id="0a62c-126">这些 UI 组合微服务中的每一个都类似于一个小型的 API 网关。</span><span class="sxs-lookup"><span data-stu-id="0a62c-126">Each of those UI composition microservices would be similar to a small API Gateway.</span></span> <span data-ttu-id="0a62c-127">但在此处，每个服务都负责一个小的 UI 领域。</span><span class="sxs-lookup"><span data-stu-id="0a62c-127">But in this case each one is responsible for a small UI area.</span></span>

<span data-ttu-id="0a62c-128">由微服务驱动的复合 UI 方法的挑战性可能更大也可能更小，具体取决于使用的 UI 技术。</span><span class="sxs-lookup"><span data-stu-id="0a62c-128">A composite UI approach that's driven by microservices can be more challenging or less so, depending on what UI technologies you're using.</span></span> <span data-ttu-id="0a62c-129">例如，生成传统 Web 应用程序时，不会采用生成 SPA 或本机移动应用的技术（开发 Xamarin 应用时，此方法可能更具挑战性）。</span><span class="sxs-lookup"><span data-stu-id="0a62c-129">For instance, you won't use the same techniques for building a traditional web application that you use for building an SPA or for native mobile app (as when developing Xamarin apps, which can be more challenging for this approach).</span></span>

<span data-ttu-id="0a62c-130">出于多种原因，[eShopOnContainers](https://aka.ms/MicroservicesArchitecture) 示例应用程序使用整体式 UI 方法。</span><span class="sxs-lookup"><span data-stu-id="0a62c-130">The [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) sample application uses the monolithic UI approach for multiple reasons.</span></span> <span data-ttu-id="0a62c-131">首先，其作用是引入微服务和容器。</span><span class="sxs-lookup"><span data-stu-id="0a62c-131">First, it's an introduction to microservices and containers.</span></span> <span data-ttu-id="0a62c-132">虽然复合 UI 更高级，但该 UI 的设计和开发工作也更复杂。</span><span class="sxs-lookup"><span data-stu-id="0a62c-132">A composite UI is more advanced but also requires further complexity when designing and developing the UI.</span></span> <span data-ttu-id="0a62c-133">其次，eShopOnContainers 还提供了基于 Xamarin 的本机移动应用，这增加了客户端 C\# 的复杂性。</span><span class="sxs-lookup"><span data-stu-id="0a62c-133">Second, eShopOnContainers also provides a native mobile app based on Xamarin, which would make it more complex on the client C\# side.</span></span>

<span data-ttu-id="0a62c-134">不过，建议通过以下参考资料，深入了解基于微服务的复合 UI。</span><span class="sxs-lookup"><span data-stu-id="0a62c-134">However, we encourage you to use the following references to learn more about composite UI based on microservices.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0a62c-135">其他资源</span><span class="sxs-lookup"><span data-stu-id="0a62c-135">Additional resources</span></span>

- <span data-ttu-id="0a62c-136">**使用 ASP.NET（Particular 的 Workshop）的复合 UI** </span><span class="sxs-lookup"><span data-stu-id="0a62c-136">**Composite UI using ASP.NET (Particular's Workshop)** </span></span>\
  <https://github.com/Particular/Workshop/tree/master/demos/asp-net-core>

- <span data-ttu-id="0a62c-137">**Ruben Oostinga。The Monolithic Frontend in the Microservices Architecture** \（微服务体系结构中的整体式前端）</span><span class="sxs-lookup"><span data-stu-id="0a62c-137">**Ruben Oostinga. The Monolithic Frontend in the Microservices Architecture** \</span></span>
  <https://xebia.com/blog/the-monolithic-frontend-in-the-microservices-architecture/>

- <span data-ttu-id="0a62c-138">**Mauro Servienti。The secret of better UI composition** \（优化 UI 组合的秘诀）</span><span class="sxs-lookup"><span data-stu-id="0a62c-138">**Mauro Servienti. The secret of better UI composition** \</span></span>
  <https://particular.net/blog/secret-of-better-ui-composition>

- <span data-ttu-id="0a62c-139">**Viktor Farcic。Including Front-End Web Components Into Microservices** \（在微服务中纳入前端 Web 组件）</span><span class="sxs-lookup"><span data-stu-id="0a62c-139">**Viktor Farcic. Including Front-End Web Components Into Microservices** \</span></span>
  <https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/>

- <span data-ttu-id="0a62c-140">**Managing Frontend in the Microservices Architecture** \（在微服务体系结构中管理前端）</span><span class="sxs-lookup"><span data-stu-id="0a62c-140">**Managing Frontend in the Microservices Architecture** \</span></span>
  <https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html>

>[!div class="step-by-step"]
><span data-ttu-id="0a62c-141">[上一页](microservices-addressability-service-registry.md)
>[下一页](resilient-high-availability-microservices.md)</span><span class="sxs-lookup"><span data-stu-id="0a62c-141">[Previous](microservices-addressability-service-registry.md)
[Next](resilient-high-availability-microservices.md)</span></span>