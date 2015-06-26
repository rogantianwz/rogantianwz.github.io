---
layout: post
category: pattern
tagline: ""
tags: [pattern]
---
{% include JB/setup %}

直接上代码吧，还有很多优化的地方，目前先实现功能，能过滤大部分常用的emoji表情符号

```
public class FilterEmojiMethod {

	private static String regex = "[\ud83c\udc00-\ud83c\udfff]|[\ud83d\udc00-\ud83d\udfff]|[\u25b6-\u25c0]" 
							+ "|[\u25e9-\u25ec]|[\u23e9-\u23ec]|[\u2b05-\u2b07]|[\u27a1]|[\u2194-\u2199]"
						    + "|[\u2934-\u2935]|[\u21a9-\u21aa]|[\u200d]|[\u2764\ufe0f]|[\u261d]|[\u270a-\u270c]"
						    + "|[\u2600-\u2615]|[\u2648-\u264f]|[\u2764\ufe0f]|[\u261d]|[\u270a-\u270c]"
						    + "|[\u2600-\u2615]|[\u26a0-\u26a1]|[\u26aa-\u26ab]|[\u26c4-\u26c5]|[\u26ce]"
						    + "|[\u25fb-\u25fe]|[\u2753-\u2757]|[\u2744-\u274f]|[\u2b50]|[\u26f2-\u26fa]"
						    + "|[\u26bd-\u26be]|[\u2708-\u270f]|[\u2728]|[\u26bd-\u26be]|[\u26fd]|[\u3297-\u3299]|[\u2650-\u2653]"
							+ "|[\u2693]|[\u26ea]|[\u231a]|[\u23f0]|[\u23f3]|[\u231b]|[\u2702]|[\u2712]|[\u26d4]|[\u2733]|[\u2705]|[\u2734]"
							+ "|[\u2668]|[\u267b]|[\u2660]|[\u2663]|[\u2665]|[\u2666]|[\u25aa]|[\u25ab]|[\u2b1b]|[\u2b1c]|[\u267f]|[\u2b55]"
						    + "|[\u24c2]|[\u2139]|[\u2795]|[\u2796]|[\u3030]|[\u2797]|[\u2716]|[\u2714]|[\u2122]|[\u27b0]|[\u27bf]|[\u303d]"
							+ "|[\u20e3]|[\u263a]";
	private static Pattern pattern = Pattern.compile(regex, Pattern.UNICODE_CASE | Pattern.CASE_INSENSITIVE);

	public static String filter(String inputString) {
		return pattern.matcher(inputString).replaceAll("");
	}
}
```
