<script setup lang="ts">
import { Head, Link } from '@inertiajs/vue3';
import { dashboard, login, register } from '@/routes';
import { 
    BrainCircuit, 
    MonitorSmartphone, 
    TrendingUp, 
    Users,
    CheckCircle2
} from 'lucide-vue-next';

withDefaults(
    defineProps<{
        canRegister?: boolean;
    }>(),
    {
        canRegister: true,
    },
);
</script>

<template>
    <Head title="Skillability - Learn faster. Apply better." />
    <div class="min-h-screen bg-[#0f1117] text-white font-sans selection:bg-blue-500/30">
        <!-- Header -->
        <header class="container mx-auto px-6 py-6 flex items-center justify-between">
            <div class="flex items-center gap-2">
                <span class="text-xl font-bold tracking-tight">Skillability</span>
            </div>
            
            <nav class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-300">
                <a href="#features" class="hover:text-white transition-colors">Features</a>
                <a href="#process" class="hover:text-white transition-colors">Process</a>
                <a href="#benefits" class="hover:text-white transition-colors">Benefits</a>
                <a href="#pricing" class="hover:text-white transition-colors">Pricing</a>
            </nav>

            <div class="flex items-center gap-4">
                <Link
                    v-if="$page.props.auth?.user"
                    :href="dashboard()"
                    class="bg-blue-600 hover:bg-blue-500 text-white px-5 py-2.5 rounded-lg text-sm font-medium transition-all shadow-[0_0_15px_rgba(37,99,235,0.3)]"
                >
                    Dashboard
                </Link>
                <template v-else>
                    <Link
                        :href="login()"
                        class="bg-blue-600 hover:bg-blue-500 text-white px-5 py-2.5 rounded-lg text-sm font-medium transition-all shadow-[0_0_15px_rgba(37,99,235,0.3)]"
                    >
                        Get Started
                    </Link>
                </template>
            </div>
        </header>

        <!-- Hero Section -->
        <main class="container mx-auto px-6 pt-20 pb-32">
            <div class="flex flex-col lg:flex-row items-center gap-16">
                <div class="flex-1 space-y-8">
                    <h1 class="text-5xl md:text-6xl font-bold leading-[1.1] tracking-tight">
                        Learn <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-blue-500">faster</span>.<br/>
                        Apply <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-blue-500">better</span>.
                    </h1>
                    <p class="text-lg text-gray-400 max-w-xl leading-relaxed">
                        Unlock the power of neural-optimized learning environments designed to accelerate your mastery of complex skills through AI-driven adaptation and real-world synthesis.
                    </p>
                    <div class="flex items-center gap-4 pt-4">
                        <Link
                            v-if="canRegister"
                            :href="register()"
                            class="bg-blue-600 hover:bg-blue-500 text-white px-8 py-3.5 rounded-lg font-medium transition-all shadow-[0_0_20px_rgba(37,99,235,0.4)]"
                        >
                            Join the Mission
                        </Link>
                        <a
                            href="#courses"
                            class="px-8 py-3.5 rounded-lg font-medium border border-gray-700 hover:border-gray-500 hover:bg-white/5 transition-all text-white"
                        >
                            View Courses
                        </a>
                    </div>
                </div>
                <div class="flex-1 relative">
                    <div class="absolute inset-0 bg-blue-500/20 blur-[100px] rounded-full"></div>
                    <img src="/images/rocket_hero.png" alt="Futuristic Rocket taking off" class="relative z-10 w-full max-w-lg mx-auto rounded-2xl shadow-2xl border border-white/10" />
                </div>
            </div>
        </main>

        <!-- The Cognitive Edge Section -->
        <section id="features" class="container mx-auto px-6 py-24">
            <div class="text-center mb-16">
                <h2 class="text-3xl font-bold tracking-tight">The Cognitive Edge</h2>
                <div class="h-1 w-12 bg-blue-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Feature 1 -->
                <div class="bg-[#151821] p-8 rounded-2xl border border-white/5 hover:border-blue-500/30 transition-colors group">
                    <div class="w-12 h-12 bg-blue-500/10 rounded-xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                        <BrainCircuit class="w-6 h-6 text-blue-400" />
                    </div>
                    <h3 class="text-xl font-semibold mb-3">Adaptive Learning</h3>
                    <p class="text-gray-400 text-sm leading-relaxed">Proprietary algorithms that adjust content difficulty in real-time based on your cognitive load.</p>
                </div>

                <!-- Feature 2 -->
                <div class="bg-[#151821] p-8 rounded-2xl border border-white/5 hover:border-blue-500/30 transition-colors group">
                    <div class="w-12 h-12 bg-cyan-500/10 rounded-xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                        <MonitorSmartphone class="w-6 h-6 text-cyan-400" />
                    </div>
                    <h3 class="text-xl font-semibold mb-3">Real-world Projects</h3>
                    <p class="text-gray-400 text-sm leading-relaxed">Translate theory into reality with simulated industry environments and high-stakes deliverables.</p>
                </div>

                <!-- Feature 3 -->
                <div class="bg-[#151821] p-8 rounded-2xl border border-white/5 hover:border-blue-500/30 transition-colors group">
                    <div class="w-12 h-12 bg-indigo-500/10 rounded-xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                        <TrendingUp class="w-6 h-6 text-indigo-400" />
                    </div>
                    <h3 class="text-xl font-semibold mb-3">Neural Progress</h3>
                    <p class="text-gray-400 text-sm leading-relaxed">Advanced telemetry-inspired dashboards tracking your retention rates and skill fluency depth.</p>
                </div>

                <!-- Feature 4 -->
                <div class="bg-[#151821] p-8 rounded-2xl border border-white/5 hover:border-blue-500/30 transition-colors group">
                    <div class="w-12 h-12 bg-purple-500/10 rounded-xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                        <Users class="w-6 h-6 text-purple-400" />
                    </div>
                    <h3 class="text-xl font-semibold mb-3">Expert Mentorship</h3>
                    <p class="text-gray-400 text-sm leading-relaxed">Direct line to top-tier industry veterans for peer-review and career strategic guidance.</p>
                </div>
            </div>
        </section>

        <!-- Our Acceleration Process -->
        <section id="process" class="py-24 bg-[#0a0c10]">
            <div class="container mx-auto px-6">
                <div class="text-center mb-20">
                    <h2 class="text-3xl font-bold tracking-tight mb-4">Our Acceleration Process</h2>
                    <p class="text-gray-400 max-w-2xl mx-auto">A seamless transition from novice to master in three distinct phases.</p>
                </div>

                <div class="flex flex-col md:flex-row items-start justify-center gap-8 relative max-w-4xl mx-auto">
                    <!-- Connecting Line -->
                    <div class="hidden md:block absolute top-8 left-[10%] right-[10%] h-[1px] bg-gradient-to-r from-transparent via-gray-700 to-transparent"></div>

                    <!-- Step 1 -->
                    <div class="flex-1 flex flex-col items-center text-center relative z-10">
                        <div class="w-16 h-16 rounded-full bg-[#151821] border border-gray-700 flex items-center justify-center text-gray-400 font-mono mb-6">
                            01
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Learn</h3>
                        <p class="text-gray-400 text-sm">Absorb concepts through micro-learning modules optimized for maximum retention.</p>
                    </div>

                    <!-- Step 2 -->
                    <div class="flex-1 flex flex-col items-center text-center relative z-10">
                        <div class="w-16 h-16 rounded-full bg-[#151821] border border-blue-500/50 flex items-center justify-center text-blue-400 font-mono mb-6 shadow-[0_0_15px_rgba(37,99,235,0.2)]">
                            02
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Practice</h3>
                        <p class="text-gray-400 text-sm">Apply theoretical knowledge in sandbox environments with instant AI feedback.</p>
                    </div>

                    <!-- Step 3 -->
                    <div class="flex-1 flex flex-col items-center text-center relative z-10">
                        <div class="w-16 h-16 rounded-full bg-[#151821] border border-green-500/50 flex items-center justify-center text-green-400 font-mono mb-6 shadow-[0_0_15px_rgba(34,197,94,0.2)]">
                            03
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Master</h3>
                        <p class="text-gray-400 text-sm">Prove competency through capstone challenges that mirror real world demands.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Industry Results Section -->
        <section class="container mx-auto px-6 py-32">
            <div class="flex flex-col lg:flex-row items-center gap-16">
                <div class="flex-1 relative">
                    <div class="absolute -inset-4 bg-cyan-500/10 blur-[50px] rounded-full"></div>
                    <img src="/images/dashboard_analytics.png" alt="Analytics Dashboard" class="relative z-10 w-full rounded-2xl border border-white/10 shadow-2xl shadow-cyan-500/10" />
                </div>
                <div class="flex-1 space-y-6">
                    <span class="text-cyan-400 text-sm font-bold tracking-wider uppercase">Industry Results</span>
                    <h2 class="text-4xl md:text-5xl font-bold tracking-tight">90% Faster Skill<br/>Acquisition</h2>
                    <p class="text-gray-400 text-lg">
                        Our students outperform traditional bootcamp and university graduates by leveraging cognitive science models that reduce learning fatigue and maximize synaptic encoding.
                    </p>
                    <div class="space-y-4 pt-4">
                        <div class="flex gap-4 items-start">
                            <CheckCircle2 class="w-6 h-6 text-green-400 shrink-0 mt-0.5" />
                            <div>
                                <h4 class="font-semibold text-white">Industry-Ready Outputs</h4>
                                <p class="text-sm text-gray-400">Every graduate completes a portfolio of 5+ production-grade projects reviewed by experts.</p>
                            </div>
                        </div>
                        <div class="flex gap-4 items-start">
                            <CheckCircle2 class="w-6 h-6 text-green-400 shrink-0 mt-0.5" />
                            <div>
                                <h4 class="font-semibold text-white">Lifelong Learning Network</h4>
                                <p class="text-sm text-gray-400">Continuous access to updated curriculum modules as technology stacks evolve over time.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- CTA Section -->
        <section class="container mx-auto px-6 pb-32 pt-16">
            <div class="relative rounded-3xl overflow-hidden bg-gradient-to-br from-[#1c2237] to-[#0f1117] border border-white/10 p-12 md:p-20 text-center">
                <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-full max-w-2xl bg-blue-500/20 blur-[120px] rounded-full pointer-events-none"></div>
                
                <div class="relative z-10 space-y-6 max-w-2xl mx-auto">
                    <h2 class="text-4xl font-bold tracking-tight">Accelerate Your Intelligence</h2>
                    <p class="text-gray-400 text-lg">
                        Join 10,000+ engineers, designers, and strategists who have redefined their career trajectory with Skillability's intellectual acceleration framework.
                    </p>
                    <div class="flex flex-col sm:flex-row items-center justify-center gap-4 pt-6">
                        <Link
                            v-if="canRegister"
                            :href="register()"
                            class="w-full sm:w-auto bg-blue-500 hover:bg-blue-400 text-white px-8 py-4 rounded-xl font-medium transition-all shadow-[0_0_20px_rgba(59,130,246,0.3)] text-center"
                        >
                            Start Your Free Trial
                        </Link>
                        <a
                            href="#contact"
                            class="w-full sm:w-auto px-8 py-4 rounded-xl font-medium border border-white/10 bg-white/5 hover:bg-white/10 transition-all text-white text-center"
                        >
                            Contact Enterprise Sales
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="border-t border-white/10 bg-[#0a0c10] py-12">
            <div class="container mx-auto px-6 flex flex-col md:flex-row items-center justify-between gap-6">
                <div class="flex flex-col gap-2">
                    <span class="text-xl font-bold tracking-tight text-white">Skillability</span>
                    <p class="text-sm text-gray-500 max-w-xs">
                        Empowering the next generation of digital architects through precision-engineered learning paths.
                    </p>
                </div>
                
                <div class="flex gap-8 text-sm text-gray-400">
                    <a href="#" class="hover:text-white transition-colors">Platform</a>
                    <a href="#" class="hover:text-white transition-colors">Resources</a>
                    <a href="#" class="hover:text-white transition-colors">Company</a>
                    <a href="#" class="hover:text-white transition-colors">Privacy Policy</a>
                    <a href="#" class="hover:text-white transition-colors">Terms of Service</a>
                </div>

                <div class="text-sm text-gray-500">
                    &copy; 2026 Skillability. Intellectual Acceleration.
                </div>
            </div>
        </footer>
    </div>
</template>
