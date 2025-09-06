\documentclass[aspectratio=169]{beamer}
\usepackage[utf8]{inputenc}
\usepackage{tikz}
\usepackage{fontawesome5}
\usepackage{hyperref}
\usepackage{xcolor}
\usepackage{graphicx}
\usepackage{colortbl}
\usepackage{listings}
\usepackage{adjustbox} % Added for better block alignment

% Define Google Colors
\definecolor{googleblue}{RGB}{66, 133, 244}
\definecolor{googlered}{RGB}{234, 67, 53}
\definecolor{googleyellow}{RGB}{251, 188, 5}
\definecolor{googlegreen}{RGB}{52, 168, 83}
\definecolor{darkgrey}{RGB}{95, 99, 104}
\definecolor{lightgrey}{RGB}{241, 243, 244}

% Theme Settings
\usetheme{Madrid}
\usecolortheme[named=googleblue]{structure}

% Remove navigation symbols
\setbeamertemplate{navigation symbols}{}

% Consistent block padding
\setbeamertemplate{block begin}{\begin{adjustbox}{max width=0.95\textwidth,keepaspectratio}\begin{minipage}{\textwidth}\vspace{0.5em}}
\setbeamertemplate{block end}{\vspace{0.5em}\end{minipage}\end{adjustbox}}
\setbeamertemplate{alertblock begin}{\begin{adjustbox}{max width=0.95\textwidth,keepaspectratio}\begin{minipage}{\textwidth}\vspace{0.5em}}
\setbeamertemplate{alertblock end}{\vspace{0.5em}\end{minipage}\end{adjustbox}}
\setbeamertemplate{exampleblock begin}{\begin{adjustbox}{max width=0.95\textwidth,keepaspectratio}\begin{minipage}{\textwidth}\vspace{0.5em}}
\setbeamertemplate{exampleblock end}{\vspace{0.5em}\end{minipage}\end{adjustbox}}

% Header configuration
\setbeamertemplate{headline}{
    \leavevmode%
    \hbox{%
        \begin{beamercolorbox}[wd=.5\paperwidth,ht=2.5ex,dp=1ex,left]{section in head/foot}%
            \hspace{1em}\insertframenumber/\inserttotalframenumber\hspace{1em}
        \end{beamercolorbox}%
        \begin{beamercolorbox}[wd=.5\paperwidth,ht=2.5ex,dp=1ex,right]{subsection in head/foot}%
            \hspace{1em}\insertshorttitle\hspace{1em}
        \end{beamercolorbox}%
    }%
}

% Footer configuration with blue background and white text
\setbeamertemplate{footline}{
    \leavevmode%
    \hbox{%
        \begin{beamercolorbox}[wd=\paperwidth,ht=3ex,dp=1.5ex,center,colorbg=googleblue,colorfg=white]{footer}%
            \begin{minipage}{0.33\textwidth}
                \raggedright
                \hspace{1em}\href{https://easy-ai-labs.lovable.app/}{\color{white}Easy AI Labs}
            \end{minipage}%
            \begin{minipage}{0.33\textwidth}
                \centering
                \href{https://www.linkedin.com/in/yashkavaiya}{\color{white}Yash Kavaiya}
            \end{minipage}%
            \begin{minipage}{0.33\textwidth}
                \raggedleft
                \href{https://www.linkedin.com/company/genai-guru}{\color{white}Gen AI Guru}\hspace{1em}
            \end{minipage}
        \end{beamercolorbox}%
    }%
}

% Title and author information
\title[Planning for Conversational Agents]{Planning for Conversational Agents}
\subtitle{Complete Quiz Guide with Explanations}
\author{Presented by Yash Kavaiya}
\institute{Easy AI Labs \& Gen AI Guru}
\date{\today}

% Hyperref setup
\hypersetup{
    colorlinks=true,
    linkcolor=white,
    urlcolor=white,
    citecolor=white
}

\begin{document}

% Title Slide with Custom Design
\begin{frame}[plain]
    \begin{tikzpicture}[remember picture,overlay]
        % Background gradient
        \fill[googleblue] (current page.north west) rectangle (current page.south east);
        
        % Google colors accent bars
        \fill[googlered] ([yshift=-2cm]current page.north west) rectangle ++(0.4cm, -7cm);
        \fill[googleyellow] ([yshift=-2cm, xshift=0.5cm]current page.north west) rectangle ++(0.4cm, -7cm);
        \fill[googlegreen] ([yshift=-2cm, xshift=1cm]current page.north west) rectangle ++(0.4cm, -7cm);
        
        % Main content
        \node[white, font=\Huge\bfseries, text width=0.8\paperwidth, align=center] at ([yshift=2cm]current page.center) {Planning for};
        \node[white, font=\LARGE, text width=0.8\paperwidth, align=center] at ([yshift=0.5cm]current page.center) {Conversational Agents};
        \node[white, font=\large, text width=0.8\paperwidth, align=center] at ([yshift=-0.8cm]current page.center) {Architecture \& Deployment Guide};
        
        % Icon
        \node[white] at ([yshift=-2.5cm]current page.center) {\Huge\faRobot};
        
        % Author info
        \node[white, font=\normalsize, text width=0.8\paperwidth, align=center] at ([yshift=-4.5cm]current page.center) {
            Presented by: Yash Kavaiya
        };
        \node[white, font=\small, text width=0.8\paperwidth, align=center] at ([yshift=-5.5cm]current page.center) {
            Easy AI Labs | Gen AI Guru | \faCalendar\ \today
        };
    \end{tikzpicture}
\end{frame}

% Quiz Overview
\begin{frame}{Quiz Overview}
    \begin{columns}[t]
        \column{0.48\textwidth}
        \begin{block}{Topics Covered}
            \begin{enumerate}
                \item Omni-Channel Architecture
                \item Google Cloud Foundation
                \item Multi-Region Deployment
                \item High Availability Patterns
            \end{enumerate}
        \end{block}
        
        \column{0.48\textwidth}
        \begin{block}{Learning Objectives}
            \begin{itemize}
                \item Understand omni-channel benefits
                \item Master deployment foundations
                \item Learn multi-region strategies
                \item Apply best practices
            \end{itemize}
        \end{block}
    \end{columns}
    
    \vspace{1em}
    \begin{center}
        \begin{tikzpicture}
            \draw[fill=googleyellow, draw=googleyellow] (0,0) rectangle (10,0.5);
            \node[darkgrey, font=\bfseries] at (5,0.25) {Master the Planning Phase!};
        \end{tikzpicture}
    \end{center}
\end{frame}

% Topic 1: Omni-Channel Architecture
\begin{frame}{Topic 1: Omni-Channel Architecture}
    \begin{columns}[t]
        \column{0.58\textwidth}
        \begin{block}{What is Omni-Channel?}
            A unified approach to customer engagement across multiple communication channels
        \end{block}
        
        \begin{block}{Key Benefits}
            \begin{itemize}
                \item[\textcolor{googlegreen}{\faCheck}] Seamless experience across channels
                \item[\textcolor{googlegreen}{\faCheck}] Consistent customer service
                \item[\textcolor{googlegreen}{\faCheck}] Channel-specific optimization
                \item[\textcolor{googlegreen}{\faCheck}] Unified conversation history
                \item[\textcolor{googlegreen}{\faCheck}] Better customer insights
            \end{itemize}
        \end{block}
        
        \column{0.38\textwidth}
        \begin{center}
            \begin{tikzpicture}[scale=0.8, every node/.style={align=center}]
                % Center hub
                \node[draw=googleblue, fill=googleblue!20, circle, minimum width=2cm] (hub) at (0,0) {\textbf{Agent}};
                
                % Channels (positioned relative to hub)
                \node[draw=googlegreen, fill=lightgrey, rounded corners, minimum width=1.5cm] (web) at (0,2.5) {\faGlobe\ Web};
                \node[draw=googlegreen, fill=lightgrey, rounded corners, minimum width=1.5cm] (phone) at (2.5,1.25) {\faPhone\ Phone};
                \node[draw=googlegreen, fill=lightgrey, rounded corners, minimum width=1.5cm] (chat) at (2.5,-1.25) {\faComments\ Chat};
                \node[draw=googlegreen, fill=lightgrey, rounded corners, minimum width=1.5cm] (email) at (0,-2.5) {\faEnvelope\ Email};
                \node[draw=googlegreen, fill=lightgrey, rounded corners, minimum width=1.5cm] (social) at (-2.5,-1.25) {\faFacebook\ Social};
                \node[draw=googlegreen, fill=lightgrey, rounded corners, minimum width=1.5cm] (app) at (-2.5,1.25) {\faMobile\ App};
                
                % Connections
                \draw[->] (hub) -- (web);
                \draw[->] (hub) -- (phone);
                \draw[->] (hub) -- (chat);
                \draw[->] (hub) -- (email);
                \draw[->] (hub) -- (social);
                \draw[->] (hub) -- (app);
            \end{tikzpicture}
        \end{center}
    \end{columns}
\end{frame}

% Question 1 - Part 1: Question
\begin{frame}{Question 1: Omni-Channel Benefits}
    \begin{center}
        \begin{tikzpicture}
            \node[draw=googleblue, fill=lightgrey, rounded corners, minimum width=12cm, minimum height=2cm, text=darkgrey, font=\Large\bfseries, text width=11cm, align=center] {
                What is NOT a benefit of using Omni-Channel?
            };
        \end{tikzpicture}
    \end{center}
    
    \vspace{0.5em}
    
    \begin{columns}[t]
        \column{0.48\textwidth}
        \begin{block}{Option A}
            \raggedright
            \textcolor{googlered}{\faTimesCircle} Tune responses for each channel
        \end{block}
        
        \begin{block}{Option B}
            \raggedright
            \textcolor{googlered}{\faTimesCircle} Providing a more seamless and integrated experience across channels
        \end{block}
        
        \column{0.48\textwidth}
        \begin{block}{Option C}
            \raggedright
            \textcolor{googlered}{\faTimesCircle} Improve the accuracy and consistency of customer service across channels
        \end{block}
        
        \begin{block}{Option D}
            \raggedright
            \textcolor{googlegreen}{\faCheckCircle} \textbf{Agent high availability}
        \end{block}
    \end{columns}
\end{frame}

% Question 1 - Part 2: Answer & Explanation
\begin{frame}{Question 1: Answer Explanation}
    \begin{alertblock}{Correct Answer: D - Agent high availability}
        \textcolor{googlegreen}{\faCheckCircle} High availability is an infrastructure concern, NOT an omni-channel benefit
    \end{alertblock}
    
    \begin{columns}[t]
        \column{0.48\textwidth}
        \begin{block}{TRUE Omni-Channel Benefits}
            \begin{itemize}
                \item[\textcolor{googlegreen}{\faCheck}] Channel-specific tuning
                \item[\textcolor{googlegreen}{\faCheck}] Seamless experience
                \item[\textcolor{googlegreen}{\faCheck}] Consistent service
                \item[\textcolor{googlegreen}{\faCheck}] Unified data
            \end{itemize}
        \end{block}
        
        \column{0.48\textwidth}
        \begin{block}{What High Availability IS}
            \begin{itemize}
                \item Infrastructure feature
                \item Redundancy strategy
                \item Uptime guarantee
                \item Separate from channel strategy
            \end{itemize}
        \end{block}
    \end{columns}
    
    \begin{exampleblock}{Key Insight}
        Omni-channel focuses on customer experience across channels. High availability focuses on system uptime and is achieved through different architectural patterns like multi-region deployment.
    \end{exampleblock}
\end{frame}

% Topic 2: Google Cloud Foundation
\begin{frame}{Topic 2: Google Cloud Foundation for Conversational Agents}
    \begin{center}
        \textbf{\Large The Three Pillars of Foundation}
    \end{center}
    
    \vspace{0.5em}
    
    \begin{columns}[t]
        \column{0.32\textwidth}
        \begin{center}
            \begin{tikzpicture}
                \node[draw=googleblue, fill=googleblue!20, rounded corners, minimum width=3.5cm, minimum height=4cm] {
                    \begin{minipage}{3.2cm}
                        \centering
                        \textcolor{googleblue}{\Huge\faNetworkWired}\\[0.5em]
                        \textbf{NETWORK}\\[0.3em]
                        \small
                        • VPC Design\\
                        • Connectivity\\
                        • Load Balancing\\
                        • CDN Strategy\\
                        • Latency Optimization
                    \end{minipage}
                };
            \end{tikzpicture}
        \end{center}
        
        \column{0.32\textwidth}
        \begin{center}
            \begin{tikzpicture}
                \node[draw=googlegreen, fill=googlegreen!20, rounded corners, minimum width=3.5cm, minimum height=4cm] {
                    \begin{minipage}{3.2cm}
                        \centering
                        \textcolor{googlegreen}{\Huge\faShieldAlt}\\[0.5em]
                        \textbf{SECURITY}\\[0.3em]
                        \small
                        • IAM Policies\\
                        • Data Encryption\\
                        • DLP Integration\\
                        • Compliance\\
                        • Audit Logging
                    \end{minipage}
                };
            \end{tikzpicture}
        \end{center}
        
        \column{0.32\textwidth}
        \begin{center}
            \begin{tikzpicture}
                \node[draw=googleyellow, fill=googleyellow!20, rounded corners, minimum width=3.5cm, minimum height=4cm] {
                    \begin{minipage}{3.2cm}
                        \centering
                        \textcolor{googleyellow}{\Huge\faDollarSign}\\[0.5em]
                        \textbf{BILLING}\\[0.3em]
                        \small
                        • Cost Controls\\
                        • Budget Alerts\\
                        • Resource Quotas\\
                        • Usage Tracking\\
                        • Optimization
                    \end{minipage}
                };
            \end{tikzpicture}
        \end{center}
    \end{columns}
    
    \vspace{0.5em}
    
    \begin{alertblock}{Remember}
        These three areas form the foundation - NOT agent-specific features like Flows, Pages, or Intents
    \end{alertblock}
\end{frame}

% Question 2 - Part 1: Question
\begin{frame}{Question 2: Core Foundation Areas}
    \begin{center}
        \begin{tikzpicture}
            \node[draw=googleblue, fill=lightgrey, rounded corners, minimum width=12cm, minimum height=2cm, text=darkgrey, font=\Large\bfseries, text width=11cm, align=center] {
                What are 3 core areas to consider when deploying\\Google Cloud foundation for Conversational Agents?
            };
        \end{tikzpicture}
    \end{center}
    
    \vspace{0.5em}
    
    \begin{columns}[t]
        \column{0.48\textwidth}
        \begin{block}{Option A}
            \raggedright
            \textcolor{googlered}{\faTimesCircle} Automation, Resilience, and Disaster Recovery
        \end{block}
        
        \begin{block}{Option B}
            \raggedright
            \textcolor{googlered}{\faTimesCircle} Agent regionality, Agent resilience, and Agent personality
        \end{block}
        
        \column{0.48\textwidth}
        \begin{block}{Option C}
            \raggedright
            \textcolor{googlegreen}{\faCheckCircle} \textbf{Network, Security and Billing}
        \end{block}
        
        \begin{block}{Option D}
            \raggedright
            \textcolor{googlered}{\faTimesCircle} Flows, Pages, and Intents
        \end{block}
    \end{columns}
\end{frame}

% Question 2 - Part 2: Answer & Explanation
\begin{frame}{Question 2: Answer Explanation}
    \begin{alertblock}{Correct Answer: C - Network, Security and Billing}
        \textcolor{googlegreen}{\faCheckCircle} These are the foundational infrastructure pillars for ANY Google Cloud deployment
    \end{alertblock}
    
    \begin{block}{Why other options are incorrect:}
        \begin{itemize}
            \item[\textcolor{googlered}{\faTimes}] \textbf{Option A:} These are important but secondary considerations that come after foundation
            \item[\textcolor{googlered}{\faTimes}] \textbf{Option B:} Mix of deployment and application-level concerns
            \item[\textcolor{googlered}{\faTimes}] \textbf{Option D:} These are Dialogflow CX components, not foundation elements
        \end{itemize}
    \end{block}
    
    \begin{columns}[t]
        \column{0.32\textwidth}
        \begin{exampleblock}{Network Examples}
            \small
            \raggedright
            • Private IP ranges\\
            • Firewall rules\\
            • DNS configuration
        \end{exampleblock}
        
        \column{0.32\textwidth}
        \begin{exampleblock}{Security Examples}
            \small
            \raggedright
            • Service accounts\\
            • API restrictions\\
            • Encryption keys
        \end{exampleblock}
        
        \column{0.32\textwidth}
        \begin{exampleblock}{Billing Examples}
            \small
            \raggedright
            • Project budgets\\
            • Cost allocation\\
            • Alert thresholds
        \end{exampleblock}
    \end{columns}
\end{frame}

% Topic 3: Multi-Region Deployment
\begin{frame}{Topic 3: Multi-Region Deployment Strategy}
    \begin{block}{Why Multi-Region?}
        Deploying across multiple regions provides disaster recovery, reduces latency, and ensures business continuity
    \end{block}
    
    \begin{center}
        \begin{tikzpicture}[scale=0.9, every node/.style={align=center}]
            % Regions
            \node[draw=googleblue, fill=googleblue!20, rounded corners, minimum width=3cm, minimum height=2cm] (us) at (0,0) {
                \begin{minipage}{2.5cm}
                    \textbf{US-Central}\\
                    \small Primary\\
                    Agent v1.2
                \end{minipage}
            };
            
            \node[draw=googlegreen, fill=googlegreen!20, rounded corners, minimum width=3cm, minimum height=2cm] (eu) at (5,0) {
                \begin{minipage}{2.5cm}
                    \textbf{EU-West}\\
                    \small Secondary\\
                    Agent v1.2
                \end{minipage}
            };
            
            \node[draw=googleyellow, fill=googleyellow!20, rounded corners, minimum width=3cm, minimum height=2cm] (asia) at (10,0) {
                \begin{minipage}{2.5cm}
                    \textbf{Asia-Pacific}\\
                    \small Secondary\\
                    Agent v1.2
                \end{minipage}
            };
            
            % Load Balancer
            \node[draw=googlered, fill=googlered!20, rounded corners, minimum width=8cm, minimum height=1.5cm] (lb) at (5,3) {
                \textbf{Global Load Balancer}\\
                \small Routes traffic based on latency, health, and location
            };
            
            % Connections
            \draw[<->, thick] (lb) -- (us);
            \draw[<->, thick] (lb) -- (eu);
            \draw[<->, thick] (lb) -- (asia);
            
            % Sync arrows
            \draw[<->, dashed, googleblue] (us) -- node[below] {\tiny Manual Sync} (eu);
            \draw[<->, dashed, googleblue] (eu) -- node[below] {\tiny Manual Sync} (asia);
        \end{tikzpicture}
    \end{center}
    
    \begin{alertblock}{Critical Point}
        Multi-region does NOT automatically sync agents - you must implement synchronization!
    \end{alertblock}
\end{frame}

% Question 3 - Part 1: Question
\begin{frame}{Question 3: Multi-Region Best Practices}
    \begin{center}
        \begin{tikzpicture}
            \node[draw=googleblue, fill=lightgrey, rounded corners, minimum width=12cm, minimum height=2cm, text=darkgrey, font=\Large\bfseries, text width=11cm, align=center] {
                What are best practices for a multi-region setup?
            };
        \end{tikzpicture}
    \end{center}
    
    \vspace{0.5em}
    
    \begin{columns}[t]
        \column{0.48\textwidth}
        \begin{block}{Option A}
            \raggedright
            \textcolor{googlegreen}{\faCheckCircle} \textbf{Use a load balancer}
        \end{block}
        
        \begin{block}{Option B}
            \raggedright
            \textcolor{googlered}{\faTimesCircle} There is only a single global agent
        \end{block}
        
        \column{0.48\textwidth}
        \begin{block}{Option C}
            \raggedright
            \textcolor{googlered}{\faTimesCircle} Multi-region will take care of syncing agents using agent ID
        \end{block}
        
        \begin{block}{Option D}
            \raggedright
            \textcolor{googlered}{\faTimesCircle} Multi-region automatically takes care of failure
        \end{block}
    \end{columns}
\end{frame}

% Question 3 - Part 2: Answer & Explanation
\begin{frame}{Question 3: Answer Explanation}
    \begin{alertblock}{Correct Answer: A - Use a load balancer}
        \textcolor{googlegreen}{\faCheckCircle} Load balancers are essential for routing traffic in multi-region deployments
    \end{alertblock}
    
    \begin{block}{Why other options are incorrect:}
        \begin{itemize}
            \item[\textcolor{googlered}{\faTimes}] \textbf{Option B:} You need separate agent instances in each region
            \item[\textcolor{googlered}{\faTimes}] \textbf{Option C:} Agents do NOT sync automatically - manual process required
            \item[\textcolor{googlered}{\faTimes}] \textbf{Option D:} Failover requires configuration, not automatic
        \end{itemize}
    \end{block}
    
    \begin{columns}[t]
        \column{0.48\textwidth}
        \begin{exampleblock}{Load Balancer Benefits}
            \raggedright
            • Automatic health checks\\
            • Geographic routing\\
            • Latency-based routing\\
            • SSL termination\\
            • DDoS protection
        \end{exampleblock}
        
        \column{0.48\textwidth}
        \begin{exampleblock}{Manual Tasks Required}
            \raggedright
            • Agent synchronization\\
            • Version management\\
            • Failover configuration\\
            • Health check setup\\
            • Traffic policies
        \end{exampleblock}
    \end{columns}
\end{frame}

% Common Misconceptions
\begin{frame}{Common Misconceptions About Multi-Region}
    \begin{enumerate}
        \item[\textcolor{googlered}{\faBan}] \textbf{Myth: Automatic Synchronization}
        \begin{itemize}
            \item Reality: You must implement CI/CD pipelines
            \item Use version control for agent configurations
            \item Deploy changes to all regions manually or via automation
        \end{itemize}
        
        \item[\textcolor{googlered}{\faBan}] \textbf{Myth: Automatic Failover}
        \begin{itemize}
            \item Reality: Requires health checks configuration
            \item Need to define failover policies
            \item Must test failover scenarios regularly
        \end{itemize}
        
        \item[\textcolor{googlered}{\faBan}] \textbf{Myth: Single Global Agent}
        \begin{itemize}
            \item Reality: Each region has its own agent instance
            \item Agents are independent resources
            \item Must maintain consistency across regions
        \end{itemize}
    \end{enumerate}
    
    \begin{center}
        \begin{tikzpicture}
            \draw[fill=googleyellow, draw=googleyellow] (0,0) rectangle (10,0.6);
            \node[darkgrey, font=\bfseries] at (5,0.3) {Understanding these concepts is crucial for success!};
        \end{tikzpicture}
    \end{center}
\end{frame}

% Best Practices Summary
\begin{frame}{Multi-Region Implementation Guide}
    \begin{columns}[t]
        \column{0.48\textwidth}
        \begin{block}{\textcolor{googleblue}{\faClipboard} Planning Phase}
            \begin{enumerate}
                \item Identify target regions
                \item Assess latency requirements
                \item Plan data residency
                \item Design network topology
                \item Create budget estimates
            \end{enumerate}
        \end{block}
        
        \begin{block}{\textcolor{googlegreen}{\faCogs} Implementation}
            \begin{enumerate}
                \item Deploy agents per region
                \item Configure load balancer
                \item Set up health checks
                \item Implement monitoring
                \item Test failover scenarios
            \end{enumerate}
        \end{block}
        
        \column{0.48\textwidth}
        \begin{block}{\textcolor{googleyellow}{\faSync} Synchronization}
            \begin{enumerate}
                \item Version control system
                \item CI/CD pipelines
                \item Automated testing
                \item Rollback procedures
                \item Change management
            \end{enumerate}
        \end{block}
        
        \begin{block}{\textcolor{googlered}{\faChartLine} Operations}
            \begin{enumerate}
                \item Monitor performance
                \item Track costs per region
                \item Regular DR drills
                \item Capacity planning
                \item Documentation updates
            \end{enumerate}
        \end{block}
    \end{columns}
\end{frame}

% Architecture Best Practices
\begin{frame}{Architecture Best Practices}
    \begin{center}
        \textbf{\Large Complete Multi-Region Architecture}
    \end{center}
    
    \begin{center}
        \begin{tikzpicture}[scale=0.8, every node/.style={align=center}]
            % User layer
            \node[draw=darkgrey, fill=lightgrey, rounded corners, minimum width=4cm] (users) at (5,5) {
                \faUsers\ Global Users
            };
            
            % CDN layer
            \node[draw=googleblue, fill=googleblue!20, rounded corners, minimum width=4cm] (cdn) at (5,4) {
                CDN / Edge Cache
            };
            
            % Load Balancer
            \node[draw=googlered, fill=googlered!20, rounded corners, minimum width=6cm] (lb) at (5,3) {
                Global Load Balancer
            };
            
            % Regions
            \node[draw=googlegreen, fill=googlegreen!20, rounded corners, minimum width=2.5cm] (r1) at (1,1) {
                Region 1\\Agent
            };
            \node[draw=googlegreen, fill=googlegreen!20, rounded corners, minimum width=2.5cm] (r2) at (5,1) {
                Region 2\\Agent
            };
            \node[draw=googlegreen, fill=googlegreen!20, rounded corners, minimum width=2.5cm] (r3) at (9,1) {
                Region 3\\Agent
            };
            
            % Data layer
            \node[draw=googleyellow, fill=googleyellow!20, rounded corners, minimum width=8cm] (data) at (5,-1) {
                Shared Data Layer (Firestore/Spanner)
            };
            
            % Connections
            \draw[->] (users) -- (cdn);
            \draw[->] (cdn) -- (lb);
            \draw[->] (lb) -- (r1);
            \draw[->] (lb) -- (r2);
            \draw[->] (lb) -- (r3);
            \draw[<->] (r1) -- (data);
            \draw[<->] (r2) -- (data);
            \draw[<->] (r3) -- (data);
        \end{tikzpicture}
    \end{center}
    
    \begin{alertblock}{Key Components}
        CDN for static content → Load Balancer for routing → Regional agents → Shared data layer
    \end{alertblock}
\end{frame}

% Quiz Summary
\begin{frame}{Quiz Summary - Your Results}
    \begin{center}
        \textbf{\Large Review Your Performance}
    \end{center}
    
    \vspace{0.5em}
    
    \begin{tikzpicture}
        % Question 1 - Correct
        \node[draw=googlegreen, fill=googlegreen!20, rounded corners, minimum width=12cm, minimum height=1.8cm] at (0,3) {
            \begin{minipage}{11cm}
                \centering
                \textcolor{googlegreen}{\faCheckCircle} \textbf{Q1: Omni-Channel Non-Benefit}\\
                Your Answer: Agent high availability \textcolor{googlegreen}{\textbf{[CORRECT]}}
            \end{minipage}
        };
        
        % Question 2 - Incorrect
        \node[draw=googlered, fill=googlered!20, rounded corners, minimum width=12cm, minimum height=1.8cm] at (0,1) {
            \begin{minipage}{11cm}
                \centering
                \textcolor{googlered}{\faTimesCircle} \textbf{Q2: Core Foundation Areas}\\
                Your Answer: Flows, Pages, and Intents \textcolor{googlered}{\textbf{[INCORRECT]}}\\
                Correct: Network, Security and Billing
            \end{minipage}
        };
        
        % Question 3 - Incorrect
        \node[draw=googlered, fill=googlered!20, rounded corners, minimum width=12cm, minimum height=1.8cm] at (0,-1) {
            \begin{minipage}{11cm}
                \centering
                \textcolor{googlered}{\faTimesCircle} \textbf{Q3: Multi-Region Best Practices}\\
                Your Answer: Multi-region will sync agents using agent ID \textcolor{googlered}{\textbf{[INCORRECT]}}\\
                Correct: Use a load balancer
            \end{minipage}
        };
        
        % Score
        \node[draw=googleyellow, fill=googleyellow, text=darkgrey, rounded corners, minimum width=4cm, minimum height=1cm, font=\bfseries] at (0,-3) {
            Your Score: 33\% | Passing: 66\%
        };
    \end{tikzpicture}
\end{frame}

% Key Takeaways
\begin{frame}{Key Takeaways for Success}
    \begin{center}
        \textbf{\Large Master These Concepts}
    \end{center}
    
    \vspace{1em}
    
    \begin{columns}[t]
        \column{0.32\textwidth}
        \begin{center}
            \begin{tikzpicture}
                \node[draw=googleblue, fill=googleblue!20, circle, minimum width=3cm, minimum height=3cm] {
                    \begin{minipage}{2.5cm}
                        \centering
                        \textcolor{googleblue}{\Large\faLayerGroup}\\[0.3em]
                        \textbf{Foundation}\\
                        \small Network\\Security\\Billing
                    \end{minipage}
                };
            \end{tikzpicture}
        \end{center}
        
        \column{0.32\textwidth}
        \begin{center}
            \begin{tikzpicture}
                \node[draw=googleyellow, fill=googleyellow!20, circle, minimum width=3cm, minimum height=3cm] {
                    \begin{minipage}{2.5cm}
                        \centering
                        \textcolor{googleyellow}{\Large\faBalanceScale}\\[0.3em]
                        \textbf{Load Balance}\\
                        \small Essential for\\multi-region
                    \end{minipage}
                };
            \end{tikzpicture}
        \end{center}
        
        \column{0.32\textwidth}
        \begin{center}
            \begin{tikzpicture}
                \node[draw=googlegreen, fill=googlegreen!20, circle, minimum width=3cm, minimum height=3cm] {
                    \begin{minipage}{2.5cm}
                        \centering
                        \textcolor{googlegreen}{\Large\faHandshake}\\[0.3em]
                        \textbf{Manual Sync}\\
                        \small Not automatic!
                    \end{minipage}
                };
            \end{tikzpicture}
        \end{center}
    \end{columns}
    
    \vspace{1em}
    
    \begin{alertblock}{Remember for Next Attempt}
        \begin{itemize}
            \item Foundation = Infrastructure (Network, Security, Billing) NOT agent features
            \item Multi-region requires manual synchronization and load balancing
            \item Omni-channel is about customer experience, not infrastructure
        \end{itemize}
    \end{alertblock}
\end{frame}

% Study Tips
\begin{frame}{Study Tips for Retaking the Quiz}
    \begin{columns}[t]
        \column{0.48\textwidth}
        \begin{block}{\textcolor{googleblue}{\faBook} Focus Areas}
            \begin{enumerate}
                \item \textbf{Google Cloud Foundation}
                \begin{itemize}
                    \item Review VPC concepts
                    \item Study IAM best practices
                    \item Understand billing models
                \end{itemize}
                
                \item \textbf{Multi-Region Architecture}
                \begin{itemize}
                    \item Load balancer types
                    \item Health check configuration
                    \item Manual sync strategies
                \end{itemize}
            \end{enumerate}
        \end{block}
        
        \column{0.48\textwidth}
        \begin{block}{\textcolor{googlegreen}{\faLightbulb} Quick Tips}
            \begin{itemize}
                \item Foundation ≠ Application features
                \item Multi-region ≠ Automatic anything
                \item Load balancer = Essential component
                \item Omni-channel = Customer experience
                \item High availability = Infrastructure
            \end{itemize}
        \end{block}
        
        \begin{block}{\textcolor{googleyellow}{\faClock} Time Management}
            \begin{itemize}
                \item Read questions carefully
                \item Look for "NOT" in questions
                \item Eliminate obvious wrong answers
                \item Focus on infrastructure vs features
            \end{itemize}
        \end{block}
    \end{columns}
\end{frame}

% Additional Resources
\begin{frame}{Recommended Study Resources}
    \begin{columns}[t]
        \column{0.48\textwidth}
        \begin{block}{\textcolor{googleblue}{\faFileAlt} Documentation}
            \begin{itemize}
                \item Google Cloud Architecture Framework
                \item Load Balancing Documentation
                \item Multi-region Best Practices
                \item Network Service Tiers
                \item IAM Best Practices
            \end{itemize}
        \end{block}
        
        \begin{block}{\textcolor{googlegreen}{\faVideo} Video Resources}
            \begin{itemize}
                \item Cloud OnAir Webinars
                \item Google Cloud Next sessions
                \item Architecture Deep Dives
                \item Multi-region tutorials
            \end{itemize}
        \end{block}
        
        \column{0.48\textwidth}
        \begin{block}{\textcolor{googleyellow}{\faFlask} Hands-on Labs}
            \begin{itemize}
                \item Set up multi-region agents
                \item Configure load balancers
                \item Implement health checks
                \item Practice failover scenarios
                \item Monitor traffic distribution
            \end{itemize}
        \end{block}
        
        \begin{block}{\textcolor{googlered}{\faQuestionCircle} Practice Questions}
            \begin{itemize}
                \item Focus on infrastructure
                \item Understand the "why"
                \item Review incorrect answers
                \item Create flashcards
            \end{itemize}
        \end{block}
    \end{columns}
\end{frame}

% Follow for More Updates - Final Slide
\begin{frame}[plain]
    \begin{tikzpicture}[remember picture,overlay]
        % Background
        \fill[googleblue] (current page.north west) rectangle (current page.south east);
        
        % Title
        \node[white, font=\Huge\bfseries, text width=0.8\paperwidth, align=center] at ([yshift=3cm]current page.center) {
            Keep Learning \& Growing!
        };
        
        % Motivational Message
        \node[white, font=\large, text width=0.8\paperwidth, align=center] at ([yshift=1.5cm]current page.center) {
            \faRocket\ You're 2 questions away from passing - You've got this!
        };
        
        % Social Links
        \node[draw=white, fill=white, fill opacity=0.1, rounded corners, minimum width=12cm, minimum height=1.5cm] at ([yshift=-0.5cm]current page.center) {
            \begin{minipage}{11cm}
                \centering
                \textcolor{white}{\Large\faLinkedin\ LinkedIn Connections}\\[0.3em]
                \href{https://www.linkedin.com/in/yashkavaiya}{\textcolor{white}{\textbf{Yash Kavaiya} - AI Expert \& Educator}}\\
                \href{https://www.linkedin.com/company/genai-guru}{\textcolor{white}{\textbf{Gen AI Guru} - Join Our Community}}
            \end{minipage}
        };
        
        \node[draw=white, fill=white, fill opacity=0.1, rounded corners, minimum width=12cm, minimum height=1.5cm] at ([yshift=-2.5cm]current page.center) {
            \begin{minipage}{11cm}
                \centering
                \textcolor{white}{\Large\faYoutube\ YouTube Learning}\\[0.3em]
                \href{https://www.youtube.com/@YashKavaiya}{\textcolor{white}{\textbf{Subscribe for Weekly Tutorials}}}\\
                \textcolor{white}{\small Architecture Deep Dives | Best Practices | Live Q\&A}
            \end{minipage}
        };
        
        \node[draw=white, fill=white, fill opacity=0.1, rounded corners, minimum width=12cm, minimum height=1.5cm] at ([yshift=-4.5cm]current page.center) {
            \begin{minipage}{11cm}
                \centering
                \textcolor{white}{\Large\faLaptopCode\ Easy AI Labs}\\[0.3em]
                \href{https://easy-ai-labs.lovable.app/}{\textcolor{white}{\textbf{Practice with Real Projects}}}\\
                \textcolor{white}{\small Hands-on Labs | Real-world Scenarios | Expert Guidance}
            \end{minipage}
        };
        
        % Bottom message
        \node[white, font=\normalsize\bfseries, text width=0.8\paperwidth, align=center] at ([yshift=-6cm]current page.center) {
            \faStar\ Good luck on your next attempt! Remember: Foundation First! \faStar
        };
    \end{tikzpicture}
\end{frame}

\end{document}
