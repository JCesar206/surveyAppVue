<script setup>
import {Github, Linkedin, Mail, HomeIcon} from "lucide-vue-next";
</script>
<template>
	<footer class="w-full bg-gray-900 text-white py-4 fixed bottom-0 left-0 flex justify-around">
		<div class="flex gap-6">
			<a href="https://jcesar206.github.io/myPersonalBlog/" target="_blank" class="hover:text-pink-500">
				<HomeIcon class="w-6 h-6" />
			</a>
			<a href="" target="_blank" class="hover:text-purple-500">
				<Github class="w-6 h-6" />
			</a>
			<a href="" target="_blank" class="hover:text-pink-500">
				<Linkedin class="w-6 h-6" />
			</a>
			<a href="mailto:jcesar206@hotmail.com" class="hover:text-purple-500">
				<Mail class="w-6 h-6" />
			</a>
		</div>
		<div>
			<p class="text-sm hover:text-blue-400 font-semibold">&copy; 2025 Survey App | JulyDevops. All right reserved.</p>
		</div>
		<div>
			<p class="text-sm hover:text-blue-400 font-semibold">Made with: Vue + Tailwind + Vite</p>
		</div>
	</footer>
</template>
<script setup></script>