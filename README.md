gef_dun01,132,223,5	script	Grimm#illuvamp	110,{
	if(BaseLevel < 130){
		mes "[Grimm]",
			"This place is too dangerous for you. Please come back when you're stronger.";
		close;
	}
	
	if(illusion_vampire == 0){
		setpcblock PCBLOCK_ALL, 1;
		mes "[Mojo]",
			"Just let me read it. I'll go bring them out afterward. Please?";
		next;
		npctalk "Bah!", "Mojo#illuvamp", bc_self;
		mes "[Grimm]",
			"Just leave me alone! I know you're going to run away with it if I give it to you.";
		next;
		mes "[Mojo]",
			"I swear I'll give it back to you. Just for one minute. How about thirty seconds? Ten seconds, then?";
		next;
		mes "[Grimm]",
			"No! I'm not even going to let you touch it!";
		next;
		mes "[Mojo]",
			"Come on, Don't you trust me?";
		next;
		mes "[Grimm]",
			"No, I don't I may trust Mojo, my sister in faith, but not Mojo, the mage.";
		next;
		npctalk "Boohooo! Oh, God! I'm being treated so unfairly!", "Mojo#illuvamp", bc_self;
		mes "[Mojo]",
			"Oh, come on! You're a priest! You're supposed to have faith in everyone! Why are you treating me like a theif?";
		next;
		npctalk "He's still whispering that to me.", "Grimm#illuvamp", bc_self;
		mes "[Grimm]",
			"I only have faith in Him, and He's telling me not to trust you.";
		next;
		mes "[Mojo]",
			"I'm not having anything!";
		next;
		npctalk "Wow, I smell lies and the smell coming from you.", "Mojo#illuvamp", bc_self;
		npctalk "That's blasphemy!.", "Grimm#illuvamp", bc_self;
		mes "[Grimm]",
			"Of course not. Only his servants can hear him.";
		next;
		select("Would you be so kind as to heal me?");
		specialeffect2 EF_HEAL2;
		percentheal 100,100;
		npctalk "He's such a hypocrite. I can never trust priests again, and it's his fault.", "Mojo#illuvamp", bc_self;
		mes "[Grimm]",
			"Sure thing. Any time you want.";
		next;
		mes "["+strcharinfo(0)+"]",
			"Thank you. I'm sorry, but I heard you fighting, even from far comer of this dungeon";
		next;
		mes "[Grimm]",
			"You heard that? We must have been really loud. I suppose that wasn't very smart of us.";
		next;
		mes "[Mojo]",
			"Oh, this is great! Instead of fighting, why don't we ask this adventurer who is right?";
		next;
		npctalk "If you're busy, we'll understand.", "Mojo#illuvamp", bc_self;
		// give quest
		setquest 14652;
		illusion_vampire = 1;
		setpcblock PCBLOCK_ALL, 0;
	}else if(illusion_vampire == 1){
		setpcblock PCBLOCK_ALL, 1;
		mes "[Mojo]",
			"Adventurer, if you're not busy, would you hear us out?";
		next;
		if(select("Let me hear it.:I have to leave.") == 2){
			mes "[Mojo]",
				"Please, when you have time come back and help us..";
			setpcblock PCBLOCK_ALL, 0;
			close;
		}
		
		mes "["+strcharinfo(0)+"]",
			"Let me hear it.";
		next;
		mes "[Grimm]",
			"Okay, this is going to be a long story. Let me have some water first.";
		next;
		mes "[Grimm]",
			"Adventurer, did you know these catacombs under Geffen once were quiet and filled with special energy instead of monsters?";
		next;
		mes "[Grimm]",
			"Back then, only a couple of monsters showed up once every decade or so.";
		next;
		select("What changed that?");
		emotion ET_OHNO;
		mes "[Grimm]",
			"*Glances at Mojo*";
		next;
		emotion ET_QUESTION, getnpcid(0, "Mojo#illuvamp");
		npctalk "I had nothing to do with it.", "Mojo#illuvamp", bc_self;
		mes "[Mojo]",
			"Why are you looking at me?";
		next;
		mes "[Grimm]",
			"Some mages decided to erect an ivory tower of their own. They searched everywhere in the continent and settled on the ground above these catacombs.";
		next;
		npctalk "Oh geez, here it goes again.", "Mojo#illuvamp", bc_self;
		emotion ET_SWEAT, getnpcid(0, "Mojo#illuvamp");
		mes "[Grimm]",
			"That was the beginning of the tragedy.";
		next;
		npctalk "Enough with the lecturing. Get the to the point already.", "Mojo#illuvamp", bc_self;
		npctalk "Everything has a cause and effect. How can you expect an adventurer to understand what this is about without knowing the cause?", "Grimm#illuvamp", bc_self;
		mes "[Grimm]",
			"It's been said all mammals have curiosity that rivals their appetite, but mages.. are the worst";
		next;
		mes "[Grimm]",
			"Anyway, these mages, after they built the Geffen Tower, took notice of the blaspemous creatures that sometimes appeared in the catacombs.";
		next;
		npctalk "They were just studying.", "Mojo#illuvamp", bc_self;
		npctalk "Just studying? They could've turned the entire continent into an unholy breeding ground!", "Grimm#illuvamp", bc_self;
		mes "[Grimm]",
			"They conducted various experiments to understand the special energy that reanimated the dead.";
		next;
		mes "[Grimm]",
			"And as if the wasn't enough, those mages used their magic and replicated the reanimating process.";
		next;
		mes "[Grimm]",
			"That went horribly wrong. The special energy that surrounded the catacombs exploded, bringing back all the dead buried in them.";
		next;
		mes "[Grimm]",
			"Those arrogant mages crossed the line! They tried to play God!";
		next;
		emotion ET_ANGER, getnpcid(0, "Mojo#illuvamp");
		mes "[Mojo]",
			"Hey, I'm one of them and I'm not going to let you talk bad about my predecessors like that!";
		next;
		npctalk "It's not telling the truth when you're only telling it from your point of view.", "Mojo#illuvamp", bc_self;
		mes "[Grimm]",
			"How am I defarring them when I'm only telling the truth?";
		next;
		mes "[Grimm]",
			"What do you think, Adventurer?",
			"Would you trust someone so reckless with important tasks?";
		next;
		select("...No.");
		npctalk "You've got to listen to both sides before you judge!", "Mojo#illuvamp", bc_self;
		mes "[Mojo]",
			"But wait, Adventurer. You haven't heard my side of the story.";
		next;
		npctalk "Apparently, trying your best wasn't enough in this case.", "Grimm#illuvamp", bc_self;
		mes "[Mojo]",
			"We understand the things that we want to study can be dangerous, so we try our best to be careful!";
		next;
		npctalk "Why are you saying that? I'm talking about my predecessors!", "Mojo#illuvamp", bc_self;
		mes "[Mojo]",
			"My predecessors may have been too enthusiastic to study what's underneath their tower, but it was that enthusiasm the made Geffen grow into the city of magic that it is.";
		next;
		mes "[Mojo]",
			"Rune-Midgard is flanked by Arunafeltz and Schwarzwald, the two strongest nations of the continent, and it's magic power is what keeps them at bay.";
		next;
		mes "[Grimm]",
			"And that's the only reason that kept the church from further pressing this matter.";
		next;
		npctalk "Father Grimm, could you stop cutting in?", "Mojo#illuvamp", bc_self;
		mes "[Grimm]",
			"Even though it doesn't change the fact that you woke the dead.";
		next;
		npctalk "I can't. You're twisting the facts to make yourself look good.", "Grimm#illuvamp", bc_self;
		mes "[Mojo]",
			"Curiosty is what fuels our life. it's the seed of development.",
			"Adventurer, would you hesitate to go to a new world because it's dangerous?";
		next;
		select("I wouldn't be an adventurer if I did.");
		emotion ET_OK, getnpcid(0, "Mojo#illuvamp");
		mes "[Mojo]",
			"We mages are just like you adventurers in that sense. I knew you'd understand me.";
		next;
		mes "[Mojo]",
			"You heard that, Father Grimm. Now show me the notebook.";
		next;
		mes "[Grimm]",
			"No. Adventurer, you agreed with me that she's not trust worthy.";
		next;
		mes "[Mojo]",
			"You also agreed with me on value of curiosity.";
		next;
		select("So, what is this about?");
		mes "["+strcharinfo(0)+"]",
			"I've heard both of you, but neither of you told me what you were fighting for.";
		next;
		mes "[Grimm]",
			"Oh, I'm sorry. The Church of Rune-Midgard periodically sends its priests out to these catacombs to maintain peace.";
		next;
		mes "[Grimm]",
			"I'm one of them, and I happened to pick up a notebook just before you found us.";
		next;
		select("A notebook?");
		mes "[Grimm]",
			"Yes. It looks like it belongs to one of the Geffen Tower mages. It has Bomi written on its cover, which I think is the name of its owner.";
		next;
		mes "[Mojo]",
			"But none of my guildsmen has such a name. I read the book, and she did sound like she was one of us. Not anymore, though.";
		next;
		mes "["+strcharinfo(0)+"]",
			"Not anymore?";
		next;
		npctalk "And that was a long, long time ago.", "Mojo#illuvamp", bc_self;
		mes "[Mojo]",
			"You're pretty sharp, Adventurer. That's right I checked with my guild and found out there was someone named Bomi. She just disappeared one day, though.";
		next;
		mes "["+strcharinfo(0)+"]",
			"Do you think this notebook belongs to her? But why was it here?";
		next;
		mes "[Mojo]",
			"That was the same question we asked at first. That didn't matter anymore once we read what was written in the notebook.";
		next;
		mes "[Grimm]",
			"What's written in it is unsettling, but what's more serious is? You'll have to read it yourself. Just don't open the last page.";
		next;
		npctalk "You know that's discrimination, right? You should be ashamed of yourself!", "Mojo#illuvamp", bc_self;
		mes "[Mojo]",
			"So you're okay with this adventurer reading it, but not me.";
		next;
		mes "[Grimm]",
			"Please take a look.";
		// give quest
		completequest 14652;
		setquest 14653;
		setpcblock PCBLOCK_ALL, 0;
		illusion_vampire = 2;
		close;		
	}else if(illusion_vampire == 2){
		setpcblock PCBLOCK_ALL, 1;
		mes "I placed my hand on the notebook Father Grimm was holding. Suddenly I felt dizzy as the air around me shimmered. Carefully, I opened the notebook.";
		next;
		mes "[Daily Journal]",
			"I fainted in the middle of learning a new spell, agian.",
			"My low stamina and insufficient mana are always the problem. I thought I could make up for my weak constitution with magic. Of course, even that required some minimal stamina, but I didn't have even that.",
			"I'm so tired";
		next;
		mes "[Daily Journal]",
			"I saw Sophia drinking a mana potion. Maybe potions are the answer to my never-ending search for physical support.",
			"I wonder if ther are special potions that could improve me physically. Then, I could become stronger at last.";
		next;
		mes "[Daily Journal]",
			"All the potions I found didn't help improve my weak constitution. All they do is boost my existing strength.",
			"Maybe I should try to formulate stamina and mana potions on my own.";
		next;
		mes "[Daily Journal]",
			"I learned about the catacombs under Geffen Tower while I was in the library, reading about the tower's history.",
			"How are the dead reanimated? What kind of vital force keeps them",
			"tomorrow.";
		next;
		mes "[Daily Journal]",
			"The dead don't talk. There's nothing I can find out from them I've found traces of experiments everywhere. Some of my peers must have been here before I have. I'm espeically tired today. I'm going to bed early tonight";
		next;
		mes "[Daily Journal]",
			"The bats in the catacombs drink blood from the zombies, probably because there's nothing else to eat.",
			"Every day I spend most of my energy keeping the bloodthirsty bats at bay. I'd get killed if I didn't stay near the exit.",
			"I'm tired.";
		next;
		mes "[Daily Journal]",
			"Today, I heared some strange noise in the catacombs. The zombies and bats were strangely quiet.",
			"Maybe I should explore deeper into the catacombs tomorrow, while the monsters hide from whatever that noise is.";
		next;
		mes "That was the last entry. I took my hand off the notebook. Father Grimm closed the notebook.";
		//change quest?
		completequest 14653;
		setquest 14654;
		setpcblock PCBLOCK_ALL, 0;
		illusion_vampire = 3;
		close;
	}else if(illusion_vampire == 3){
		setpcblock PCBLOCK_ALL, 1;
		mes "["+strcharinfo(0)+"]",
			"This notebook is both a diary and research journal.";
		next;
		mes "[Grimm]",
			"Indeed. It shows how its owner studied those blaspemous creatures to create stamina and mana echancers.";
		next;
		select("Intresting.");
		npctalk "I'd love to read it myself as well.", "Mojo#illuvamp", bc_self;
		emotion ET_OK, getnpcid(0, "Mojo#illuvamp");
		mes "[Mojo]",
			"Yes, it is. My guild would love to study this notebook. Most records from the same era have been lost.";
		next;
		mes "[Grimm]",
			"The content of this notebook isn't what causes me alarm. Didn't you detect some strange energy when you touch it?";
		next;
		mes "[Grimm]",
			"This notebook is sustained with its owner's spirtual energy, and it's pulling those who gaze upon it into the world inside it.";
		next;
		npctalk "So please let me have it. I'll give it back to you after I figure that all out.", "Mojo#illuvamp", bc_self;
		mes "[Mojo]",
			"And that's why I want to see the notebook so badly. I want to know how it contains a world inside it and why it was only discovered now.";
		next;
		npctalk "Oh, you don't even bother calling me by name anymore.", "Mojo#illuvamp", bc_self;
		mes "[Grimm]",
			"Mage, you stay out of this! This notebook is taking people to some place we don't know. And the gateway is in the last page.";
		next;
		mes "[Grimm]",
			"I scanned it for any malicious intent, but I didn't sense any. I think it's owner just needs help with some unfinished business.";
		next;
		mes "["+strcharinfo(0)+"]",
			"So were you arguing about which one of you should go to that place?";
		next;
		npctalk "So I told you, I'll go bring them back. I'm stronger than I look. I can do this on my own.", "Mojo#illuvamp", bc_self;
		npctalk "No. I'd rather wait until they return.", "Grimm#illuvamp", bc_self;
		mes "[Grimm]",
			"No. The other members of my group and two mages are already there. They just haven't returned yet.";
		next;
		select("How about I go?");
		mes "[Grimm]",
			"You? Well, you're more reliable than this sister here, but are you sure?";
		next;
		mes "["+strcharinfo(0)+"]",
			"I want to repay you for healing me. Also after listening to you both, I think it's better I go. Do you want me to bring your collegues?";
		next;
		npctalk "Take me with you!", "Mojo#illuvamp", bc_self;
		mes "[Grimm]",
			"No. I just want you to find them and make sure they're okay. If they need help, please provide it to them. If they have a message for me, then please let me know.";
		next;
		npctalk "*Stares at Mojo*", "Grimm#illuvamp", bc_self;
		npctalk "Why are you staring at me?", "Mojo#illuvamp", bc_self;
		mes "[Grimm]",
			"I wish I could go with you, but my group needs me here.";
		next;
		mes "[Grimm]",
			"I can't trust her with the notebook. If something happens to it, the people inside it might not be able to come back.";
		next;
		npctalk "*Snort* Why would I do that? You're just going to run away with it.", "Grimm#illuvamp", bc_self;
		mes "[Mojo]",
			"That does it Father Grimm, put that book down. Let's fight!";
		next;
		mes "[Mojo]",
			"Then I'm going to go with the Adventurer!";
		next;
		mes "[Grimm]",
			"No. You're staying with me. Don't you dare touch the notebook.";
		next;
		emotion ET_CRY, getnpcid(0, "Mojo#illuvamp");
		mes "[Mojo]",
			"Why are you doing this to me? What have I done to you?";
		next;
		npctalk "I am worried about you.", "Grimm#illuvamp", bc_self;
		mes "[Grimm]",
			"Bother Jojo asked me to never let you touch the notebook. Do you not remember that?";
		next;
		npctalk "Go ahead.", "Grimm#illuvamp", bc_self;
		mes "[Mojo]",
			"No. I don't remember. When Sister Gem returns, I'm going to tell on you!";
		next;
		mes "[Grimm]",
			"Now, Adventurer. Let me know when you're ready.";
		
		completequest 14654;
		setquest 14655;
		illusion_vampire = 4;
		setpcblock PCBLOCK_ALL, 0;
		close;
	}else if(illusion_vampire == 13){
		if(!checkweight(25271,5)){
			mes "[Grimm]",
				"Adventurer, you seem to be carrying a lot of stuff to be talking right now..";
			next;
			mes "[Grimm]",
				"Please clear some space in your inventory.";
			close;
		}
		setpcblock PCBLOCK_ALL, 1;
		mes "[Grimm]",
			"Listen to me, or you can always go back to the Tower.";
		next;
		mes "[Mojo]",
			"No!";
		emotion ET_MERONG,getnpcid(0,"Mojo#illuvamp");
		next;
		select("Are you two still fighting?");
		mes "[Mojo]",
			"Ah, there you are! How was that place?";
		next;
		mes "[Grimm]",
			"I'm glad you came back safely, is everyone there okay?";
		npctalk "Please tell us already! I'm dying to know!","Mojo#illuvamp",bc_self;
		next;
		mes "I relayed what happened in the notebook to Father Grimm and Mojo, and told them that the others decided to keep an eye on the vampires.";
		next;
		mes "[Mojo]",
			"Wow, the same place in another plane of existence! I've never heared of this before! How does it work? This notebook has got to have something to do with it.";
		emotion ET_SPARK,getnpcid(0,"Mojo#illuvamp");
		next;
		mes "[Mojo]",
			"And vampires who understand humans? My goodness!";
		next;
		mes "[Mojo]",
			"I can't stay here. Father Grimm I have to go there. Let me go, please!";
		npctalk "Let me have the notebook.","Mojo#illuvamp",bc_self;
		next;
		mes "[Grimm]",
			"No. Never. Keep your hands to yourself.";
		npctalk "Argh! Why are you being so stubborn? I don't deserve this!";
		next;
		mes "[Grimm]",
			"Adventurer, thank you for venturing into that mysterious place for us. It'll be greatly appreciated if you visit my colleagues there bring news of them from time to time.";
		next;
		mes "[Mojo]",
			"I can do that too, you know. You just have to give me a chance!";
		npctalk "Sister Mojo, please stay out of this.","Grimm#illuvamp",bc_self;
		next;
		mes "[Grimm]",
			"Adventurer, thank you. Feel free to come to me if you want to enter the notebook again.";
		completequest 14666;
		getitem 25271,5;
		getexp 2000000,2000000;
		setpcblock PCBLOCK_ALL, 0;
		illusion_vampire = 14;
		close;	
	}else if(illusion_vampire >= 4){
		setpcblock PCBLOCK_ALL, 1;
		mes "[Grimm]",
			"Do you want to enter the notebook? Are you ready?";
		next;
		if(select("Yes, send me there.", "No.") == 2){
			mes "[Grimm]",
				"Not a problem. Just let me know when you are ready.";
			setpcblock PCBLOCK_ALL, 0;
			close;
		}
		
		mes "[Grimm]",
			"Then let me open it.";
		close2;
		
		if(checkquest(14655) != 2){
			completequest 14655;
			setquest 14656;
		}
		mes "I placed my hand on the notebook and Father Grimm opened it to the last page. Suddenly my vision got blurry as I felt my body being transported to some place.";
		sleep2 750;
		setpcblock PCBLOCK_ALL, 0;
		warp "gef_d01_i",115,217;
	}
	end;
	
OnInit:
	questinfo 14656,QTYPE_QUEST,1;
	setquestinfo_level 14656,130,175;
	questinfo 14667,QTYPE_QUEST,1;
	setquestinfo_req 14667,14666,1;
end;
}

gef_dun01,134,224,3	script	Mojo#illuvamp	123,{
	if(illusion_vampire == 14){
		.@q = checkquest(14679,HUNTING);
		disable_items;
		if(.@q > -1){
			mes "[Mojo]",
				"Adventurer, welcome back! I've been waiting for you for so long! Did you bring the things I asked? Come on, let me see them!";
			next;
			if(10 > countitem(25266) || 10 > countitem(25267)){
				mes "[Mojo]",
					"Mm, this isn't enough. Please bring me ^0000FF10 Dried Yggdrasil Leaves and 10 Suspicious Pentacles^000000.";
				next;
				mes "[Mojo]",
					"Also, could you hunt ^0000FF5 zombies of each kind^000000 for that scrowling priest over there? Thanks!";
				close;
			}
			if(.@q != 2){
				mes "[Mojo]",
					"You didn't hunt the zombies for Grimm as I asked from you to do.";
				next;
				mes "[Mojo]",
					"Please go back and hunt them, I won't tell him.",
					"Remember, ^0000FF5 zombies of each kind^000000 there.";
				close;
			}
			
			if(!checkweight(25271,1)){
				mes "- Please clear some weight before handing the quest -";
				close;
			}
			setpcblock PCBLOCK_ALL, 1;
			mes "[Mojo]",
				"Wow, these are so old and fragile, I'm afraid they might crumble in my hands.";
			next;
			mes "[Grimm]",
				"Are you happy now? They don't look any different from the ones you're using, though.";
			next;
			mes "[Mojo]",
				"You priests are the least curious kind I know. I asked for these because I wanted to compare them to the ones I have, and it takes a keen eye to catch minute differences.";
			next;
			mes "[Mojo]",
				"Adventurer, could you bring me some more tomorrow? I'm worrid I might end up damaging all these you brought today. Even if I don't, I can always use more samples.";
			next;
			mes "[Mojo]",
				"Thank you so much. See you tomorrow!";
			delitem 25266,10;
			delitem 25267,10;
			erasequest 14679;
			setquest 14680;
			getitem 25271,1;
			getexp 500000,500000;
			setpcblock PCBLOCK_ALL, 0;
			close;
		}
				
		switch(checkquest(14680,PLAYTIME)){
			case -1:
			break;
			case 0:
			case 1:
			mes "[Mojo]",
				"Hello, Adventurer.";
			next;
			mes "[Mojo]",
				"Oh, I'm sorry, but I can't talk",
				"right now. I'm too busy examining",
				"the things you brought me.";
			next;
			mes "[Mojo]",
				"Could you come back ^0000FFafer dawn^000000?";
			close;
			case 2:
			mes "[Mojo]",
				"Hello, Adventurer. How are you?";
			next;
			mes "[Mojo]",
				"Whew, I stayed up all night.",
				"examining the dried Yggdrasil leaves and the suspicious pentacles. I wouldn't have to, if Father Grimm left me alone.";
			next;
			mes "[Mojo]",
				"Anyway, they're so old and poorly",
				"preserved that they easily crumble",
				"to dust. I couldn't finish my research.";
			next;
			mes "[Mojo]",
				"So I'm thinking... Could you bring me some more today? I need ^0000FF10 Dried Yggdrasil Leaves and Suspicious Pentacles^000000.";
			next;
			mes "[Mojo]",
				"Also, please hunt 5 zombies of each kind for that priest.";
			next;
			mes "[Mojo]",
				"In the meantime, I'll catch some Z's.";
			
			setquest 14679;
			erasequest 14680;
			close;
			break;
		}
		
		mes "[Mojo]",
			"Adventurer, how did you feel when you touched the notebook? How do you think it works?";
		next;
		mes "[Mojo]",
			"I've got so many questions, but that mean priest wouldn't let me touch it.";
		next;
		mes "[Mojo]",
			"Adventurer, could you take me with you the next time you enter the notebook? I swear I'm not going to steal the notebook. I'm just really curious abou it.";
		next;
		mes "[Grimm]",
			"I can hear you. Give up your obsession with it. That would be best for you.";
		next;
		mes "[Mojo]",
			"Who says I'm obsessed with it?";
		next;
		mes "[Mojo]",
			"Adventurer, please? Don't I look pitiful?";
		next;
		if(select("What do you want to know the most?", "I don't want to get between you two.") == 2){
			mes "["+strcharinfo(0)+"]",
				"Sorry, but I don't want to get between you two. You both have a point, and I can't side with either one of you.";
			next;
			mes "[Mojo]",
				"Hmpf, alright, but if you ever feel pity for me, then come back and help me. Promise?";
			close;
		}
		mes "[Mojo]",
			"About those walking corpses, of course!";
		next;
		mes "[Mojo]",
			"I really want to know what keeps them moving, what kind of experiments my predecessors did on them, and what kind of state they're in.";
		next;
		mes "[Mojo]",
			"Such experiments are prohibited now, and all the old records were destroyed.";
		next;
		mes "[Grimm]",
			"They were destroyed for good reason. So stop wondering about them.";
		next;
		mes "[Mojo]",
			"Oh, that's right Adventurer, could you capture a zombie for me? Alive, that is.";
		npctalk "Wait, it can't be alive. It's already dead.","Mojo#illuvamp",bc_self;
		next;
		mes "[Grimm]",
			"No. Don't even think about it.",
			"Mojo, you're so close to crossing the line.";
		next;
		mes "[Mojo]",
			"I wasn't asking you! Unless you're going to let me touch the notebook, stay out of my hair!";
		next;
		mes "[Grimm]",
			"You just asked this adventurer to capture a zombie alive.";
		next;
		mes "[Grimm]",
			"You're not thinking about what kind of danger it might pose when it arrives here. You just want it because you're curious about it.";
		next;
		mes "[Grimm]",
			"Did you forget why Brother Jojo wanted you to stay here and stay away from the notebook?";
		next;
		mes "[Mojo]",
			"So I'm asking this adventurer. You keep telling me don't do this, don't do that. Is there anything I can do without you saying no?";
		npctalk "You just want me to stand here, breathing...Is that it?","Mojo#illuvamp",bc_self;
		sleep2 1000;
		npctalk "Sure, why not?","Grimm#illuvamp",bc_self;
		next;
		mes "[Grimm]",
			"You can't bring anything from the world inside the book. If you do, I'll get rid of them.";
		next;
		mes "[Grimm]",
			"If you really want to experiment on those blaspemous creatures, then I suggest you talk with Brother Jojo and the others first.";
		next;
		mes "[Mojo]",
			"When are they coming back?";
		next;
		mes "[Grimm]",
			"Beats me.";
		npctalk "You should've became a politician. You would've been more successful at that.","Mojo#illuvamp",bc_self;
		sleep2 2000;
		npctalk "I'll take that as a compliment.","Grimm#illuvamp",bc_self;
		next;
		mes "[Mojo]",
			"Adventurer, I read in the notebook that the owner used some materials to experiment on zombies. I think they're Yggdrasil leaves and some drawings.";
		next;
		select("You mean dried Yggdrasil leaves and some pentacles?");
		mes "[Mojo]",
			"Yes. Could you at least procure them for me?";
		next;
		mes "[Mojo]",
			"Maybe I can use them to figure out the experiment she did and the force that reanimates the dead.";
		npctalk "Secretly from that priest, of course","Mojo#illuvamp",bc_self;
		sleep2 3000;
		npctalk "I still can hear you.","Grimm#illuvamp",bc_self;
		sleep2 1000;
		npctalk "Stop eavesdropping on people.","Mojo#illuvamp",bc_self;
		next;
		mes "[Grimm]",
			"Why are you obsessed with this? Do you really want to let these unholy creatures loose on the continent? Do you not understand why the Tower has banned the experiments?";
		next;
		mes "[Mojo]",
			"Look, I'm not going to experiment on the zombies. I just want to take a look at the materials she used.";
		next;
		mes "[Mojo]",
			"And who knows? I might find out a way to exterminate these zombies at once.";
		npctalk "I may not look like it, but I'm pretty smart.","Mojo#illuvamp",bc_self;
		next;
		mes "[Mojo]",
			"You agreed that our enthusiasm for magic has contributed to the development of our country.";
		next;
		mes "[Grimm]",
			"...";
		npctalk "I'll take that as a yes.","Mojo#illuvamp",bc_self;
		next;
		mes "[Mojo]",
			"I promise I'm not going to do anything dangerous. I'll just take a look at the materials.";
		next;
		mes "[Grimm]",
			"I'm going to watch you.";
		next;
		mes "[Mojo]",
			"Sure, be my guest.";
		npctalk "Ooh, I'm going to be studying with you breating down my neck? How exciting!","Mojo#illuvamp",bc_self;
		next;
		mes "[Grimm]",
			"And you will stop asking me for this notebook, yes?";
		next;
		mes "[Mojo]",
			"Huh? But that's... I'd love to take a look at it.";
		npctalk "Do you think you can?","Grimm#illuvamp",bc_self;
		sleep2 1000;
		npctalk "Maybe one day, yes.","Mojo#illuvamp",bc_self;
		sleep2 1000;
		npctalk "I swear to Odin that day will never come.","Grimm#illuvamp",bc_self;
		sleep2 1000;
		npctalk "Bah!","Mojo#illuvamp",bc_self;
		next;
		select("So have you come to an agreement?");
		mes "[Mojo]",
			"Yes, we have. Please bring me some dried Yggdrasil leaves and pentacles. 10 each sounds good.";
		next;
		mes "[Grimm]",
			"Are you sure that's enough?";
		next;
		mes "[Mojo]",
			"Mm, I'm not sure yet. Do you mind if I ask for more later? Okay, then please bring me ^0000FF10 Dried Yggdrasil Leaves and 10 Suspicious Pentacles^000000.";
		next;
		mes "[Mojo]",
			"Oh, and while you're at it, could you hunt some zombies for that scowling priest as well? Just 5 of each kind. I don't want to burden you.";
		npctalk "You're already burdering him.","Grimm#illuvamp",bc_self;
		sleep2 1500;
		npctalk "Yeah, but look at you? You face lit up when I offered.";
		next;
		mes "[Mojo]",
			"Adventurer, thank you for doing this for us.";
		setquest 14679;
		close;
	}
	mes "[Mojo]",
		"The notebook... I want to see the notebook... If you enter the notebook, then you should talk to Father Grimm. If you want, I can go with you.";
	close;
	end;
OnInit:
	questinfo 14679,QTYPE_QUEST,1;
	setquestinfo_req 14679,14666,2;
end;
}

gef_d01_i,116,228,4	script	Antoine#illuvamp	669,{
	if(illusion_vampire > 4 && illusion_vampire < 14){
		mes "[Antoine]",
			"This place has so many things I want to study, I don't know where to begin. Oh my, look at that Nightmare!";
		close;
	}else if(illusion_vampire == 14){
		.@q = checkquest(14669,HUNTING);
		disable_items;
		if(.@q > -1){
			mes "[Antoine]",
				"Adventurer, I've been waiting for you! Did you get what I asked?";
			next;
			if(20 > countitem(25270)){
				mes "[Antoine]",
					"Um, you haven't found it, I see.";
				next;
				mes "[Antoine]",
					"Please bring me ^0000FF20 Wavy Manes^000000 from ^0000FFSweet Nightmares^000000.";
				next;
				mes "[Antoine]",
					"Oh, and it'll be great if you also",
					"can get rid of ^0000FF10 Sweet Nightmares^000000.",
					"I want to know how that'll affect",
					"dreams. Thank you!";
				close;
			}
			if(.@q != 2){
				mes "[Antoine]",
					"You didn't quite hunt Sweet Nightmares..";
				next;
				mes "[Antoine]",
					"Please, can you go back and hunt ^0000FF10 Sweet Nightmares^000000?",
					"I want to know how that'll affect dreams. Thank you!";
				close;
			}
			
			if(!checkweight(25271,1)){
				mes "- Please clear some weight before handing the quest -";
				close;
			}
			setpcblock PCBLOCK_ALL, 1;
			mes "[Antoine]",
				"You brought all of them. I hope I can find something out from them.";
			next;
			mes "[Antoine]",
				"These are found only inside this",
				"place. Please bring them to me",
				"whenever you can. Dreams disappear when you wake up, you know";
			next;
			mes "[Antoine]",
				"Thank you so much. You should get some rest now.";
			delitem 25270,20;
			sc_start SC_ITEMBOOST,120000,200;
			specialeffect2 EF_INCAGILITY; sc_start SC_INCREASEAGI,120000,10;
			erasequest 14669;
			setquest 14670;
			getitem 25271,1;
			getexp 500000,500000;
			setpcblock PCBLOCK_ALL, 0;
			close;
		}
		
		switch(checkquest(14670,PLAYTIME)){
			case -1:
			break;
			case 0:
			case 1:
			mes "[Antoine]",
				"Adventurer, I don't want you to strain yourself. Why don't you go get some rest?";
			next;
			mes "[Antoine]",
				"Have a good night's sleep, and come back ^0000FFafer dawn^000000.";
			close;
			case 2:
			mes "[Antoine]",
				"Adventurer. Did you have good",
				"dreams last night? I had",
				"nightmares, probably from looking at those manes all day.";
			next;
			mes "[Antoine]",
				"But I'm not about to give up!",
				"Please bring me 20 Wavy Manes as usual.";
			next;
			mes "[Antoine]",
				"Oh, and it'll be great if you also",
				"can get rid of 10 Sweet Nightmares.",
				"I want to know how that'll affect",
				"dreams. Thank you!";
				
			setquest 14669;
			erasequest 14670;
			close;
			break;
		}
		
		mes "[Antoine]",
			"Adventurer, can I talk to you for a second? I want your opinion on something.";
		next;
		if(select("Sure thing.", "I'm kind of busy") == 2){
			mes "[Antoine]",
				"Oh, are you? No problem. I can wait until you have some time for me.";
			close;
		}
		mes "[Antoine]",
			"You've seen those Nightmares and Drainliars, right? Did you notice how they look different from the kinds outside this place? Why do you think that?";
		next;
		mes "["+strcharinfo(0)+"]",
			"I don't know.";
		next;
		mes "[Antoine]",
			"Everything in this place is",
			"interesting. Especially those Sweet Nightmares. They're full of",
			"Contradictions.";
		next;
		emotion ET_SPARK,getnpcid(0,"Mojo#illuvamp");
		mes "[Antoine]",
			"Have you taken a look at their wavy mane? Look at it long enough, and you'll see flashes of images, which I belive are from other people's dreams.";
		next;
		mes "[Antoine]",
			"Sweet Nightmares... Even their name is a contradiction. Maybe their mane is the source of all nightmares.";
		next;
		mes "[Antoine]",
			"Or it could just reflect the dreams of the dead.";
		next;
		mes "[Antoine]",
			"Those two ladies may not agree, but I don't have to stay here. I'm only staying because of Sweet Nightmares.";
		next;
		mes "[Antoine]",
			"I want to get rid of their names and see if it affects our dreams.";
		next;
		mes "[Antoine]",
			"And I want to do that without",
			"having to leave my colleagues to fend for themselves. Do you know what I mean.";
		next;
		mes "["+strcharinfo(0)+"]",
			"Do you want me to ^0000FFget their manes for you^000000?";
		next;
		mes "[Antoine]",
			"Yes, please! ^0000FF20^000000 should suffice!";
		next;
		mes "[Antoine]",
			"And while you're at it, please hunt ^0000FF10 Sweet Nightmares^000000 as well. I want to know how that affects dreams.";
		next;
		mes "["+strcharinfo(0)+"]",
			"I'll do that.";
		next;
		mes "[Antoine]",
			"Thank you. In return, I'll give you some stones I've picked up from this place.";
		emotion ET_THANKS;
		next;
		mes "[Antoine]",
			"I don't know if they have any purpose, but they sure look beatiful and mysterious. Maybe someone outside this place can recognize its value.";
		next;
		mes "[Antoine]",
			"Anyway, thank you for doing this for me!";
		setquest 14669;
		close;
	}
	
	mes "[Antoine]",
		"Sister Grem, please listen to me!";
	close;
end;
OnInit:
	questinfo 14669,QTYPE_QUEST,1;
	setquestinfo_req 14669,14666,2,14670,0;
end;
OnPCLoadMapEvent:
if(strcharinfo(3)=="gef_d01_i" && checkquest(14670,PLAYTIME)==2)
	showevent QTYPE_QUEST,1;
end;
}

gef_d01_i,112,228,5	script	Marina#illuvamp	746,{
		mes "[Marina]",
			"Do you want to leave?";
		next;
		if(select("Yes.:No.") == 2){
			mes "[Marina]",
				"I see. Just let me know when you want to leave.";
			close;
		}
		mes "[Marina]",
			"So, you're in a hurry to leave. Did something happen?";
		close2;
		warp "gef_dun01",133,219;
		end;
}

gef_d01_i,113,230,5	script	Gem#illuvamp	79,{
	if(illusion_vampire == 4){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "Even if you do, I won't hear it.", "Gem#illuvamp", bc_self;
		mes "[Gem]",
			"Brother Antoine, you stay here. Sister Marina and I will go. Do either of you have a problem with that?";
		next;
		npctalk "Plus, I'm fast on my feet.", "Marina#illuvamp", bc_self;
		mes "[Marina]",
			"Brother Antoine and I will go. We're trained to fight. You are not.";
		next;
		npctalk "One of us can search while the other covers for them.", "Antoine#illuvamp", bc_self;
		mes "[Antoine]",
			"Marina, why don't you stay? Sister Gem and I will go. I think that'd be best, considering our abilities.";
		next;
		mes "[Gem]",
			"No, this place is overrun with unholy creatures. It's better if two servants of God look for them.";
		next;
		mes "[Antoine]",
			"What's that supposed to mean? Are you saying that I can't fight zombies because I'm not a servant of God?";
		next;
		mes "[Marina]",
			"How about two of us stay and one goes?";
		next;
		mes "[Gem]",
			"No, it has to be two, so they can look out for each other.";
		next;
		mes "[Antoine]",
			"What about the person left behind? They have no one to look out for them.";
		next;
		select("Excuse me. I came here of behalf of Father Grimm.");
		mes "[Marina]",
			"Did you come to help us?";
		next;
		mes "["+strcharinfo(0)+"]",
			"He's worrid that you haven't come out. He asked me to help you if you need. Did something happen?";
		next;
		mes "[Marina]",
			"We need to find some people.";
		next;
		mes "[Antoine]",
			"You can't just tell him that.",
			"Adventurer, you know what kind of place this is, don't you? We're in a hurry, so let me explain the situation to you quickly.";
		next;
		mes "[Antoine]",
			"This place is the spitting image of the Geffen catacombs, and it probably exists inside the notebook's owner memory.";
		next;
		mes "[Antoine]",
			"We came here to find out how and why this place was created.";
		next;
		mes "[Antoine]",
			"We didn't find anything peculiar about this place. We want to leave, but a couple of us -^0000FFa priest and a wizard^000000- haven't returned yet.";
		next;
		mes "[Antoine]",
			"We've searched around, but the notebook's owner memory of this place is rather hazy and inconsitent. Illusions of different wizards keep appearing, frequently and in masses.";
		next;
		mes "[Antoine]",
			"We thought it'd take forever to find them, so we decided to split up. We were discussing how we'd go about doing it when you showed up.";
		next;
		mes "[Antoine]",
			"I can't say how glad I am to have you here. Now that there are four of us, ^0000FFtwo of us can stay while the other two look^000000.";
		next;
		select("What do the missing members look like?");
		mes "[Gem]",
			"The missing priest is called ^0000FFJubilee^000000 and the wizard is ^0000FFJojo^000000. They're the typical priest and wizard. You won't miss them.";
		next;
		mes "[Marina]",
			"Adventurer, let's go!";
		next;
		mes "[Gem]",
			"Let me pray for you before you leave. Dear God, please watch over you children...";
		completequest 14656;
		setquest 14658;
		specialeffect2 EF_INCAGILITY; sc_start SC_INCREASEAGI,180000,10;
		specialeffect2 EF_BLESSING; sc_start SC_BLESSING,180000,10;
		setpcblock PCBLOCK_ALL, 0;
		illusion_vampire = 5;
		close;
	}else if(illusion_vampire >= 5 && illusion_vampire < 12){
		if(checkquest(14657) != 2 && checkquest(14658) != 2){
			mes "[Gem]",
				"I hope Brother Jubilee and Brother Jojo are safe.";
			next;
		}else if(checkquest(14663) != 2){
			mes "[Gem]",
				"I hope Brother Jojo is safe.";
			next;
		}
		
		mes "[Gem]",
			"If you have to leave, let Sister Marina know. She'll send you back to where you came from.";
		close;
	}else if(illusion_vampire == 12){
		setpcblock PCBLOCK_ALL, 1;
		mes "[Gem]",
			"Adventurer. are you leaving now?";
		next;
		select("Father Grimm must be getting anixous by now.");
		mes "["+strcharinfo(0)+"]",
			"Yes. Now that I know you're safe, it's time I return to Father Grimm.";
		next;
		mes "[Gem]",
			"According to our assessment, what happens inside this place doesn't seem to affect the outside world.";
		next;
		mes "[Gem]",
			"That's good, but someone still has to stay here to keep an eye on them. You understand us, right? Please let Brother Grimm know.";
		next;
		select("I was surprised.");
		mes "["+strcharinfo(0)+"]",
			"You're from the Church. I didn't think you'd let those vampires live.";
		next;
		mes "[Marina]",
			"If we play by the rules, then we shouldn't allow them to live.";
		next;
		mes "[Gem]",
			"She's right. We shouldn't. But looking at them... I wasn't sure if they deserved to die.";
		next;
		mes "[Gem]",
			"It's something we need to think about.";
		next;
		mes "[Marina]",
			"But if they make even the slightest mistake, we'll get rid of them!";
		emotion ET_STARE,getnpcid(0,"Marina#illuvamp");
		next;
		mes "[Antoine]",
			"If that happens, I'll let you take care of them yourself.";
		emotion ET_OK,getnpcid(0,"Antoine#illuvamp");
		next;
		mes "[Gem]",
			"Please tell Brother Grimm that we've decided to stay to keep an eye of them.";
		next;
		mes "["+strcharinfo(0)+"]",
			"I will. Stay safe.";
		//give quest 
		completequest 14665;
		setquest 14666;
		illusion_vampire = 13;
		setpcblock PCBLOCK_ALL, 0;
		close2;
		//warp to enterace
		warp "gef_dun01",133,219;
		end;
	}else if(illusion_vampire == 14){
		.@q = checkquest(14667,HUNTING);
		disable_items;
		if(.@q > -1){
			if(.@q != 2){
				mes "[Gem]",
					"Adventurer, did you take care of what I asked?";
				next;
				mes "[Gem]",
					"Or did you forget what I asked you to do?";
				next;
				mes "[Gem]",
					"Please exterminate Restless Dead.",
					"There are three different kinds",
					"Small, Fast, and Big. ^0000FFPlease",
					"exterminate 10 each^000000.";
				next;
				mes "[Gem]",
					"All the dead must return to the earth.";
				close;
			}
			
			if(!checkweight(25271,1)){
				mes "- Please clear some weight before handing the quest -";
				close;
			}
			setpcblock PCBLOCK_ALL, 1;
			mes "[Gem]",
				"Adventurer, you took care of them",
				"all. Thank you. They will also",
				"thank you from heaven.";
			next;
			mes "[Gem]",
				"Why don't you go get some reast and come back ^0000FFafer dawn^000000?";
			erasequest 14667;
			setquest 14668;
			getitem 25271,1;
			getexp 500000,500000;
			setpcblock PCBLOCK_ALL, 0;
			close;
		}
		
		switch(checkquest(14668,PLAYTIME)){
			case -1:
			break;
			case 0:
			case 1:
			mes "[Gem]",
				"Adventurer, not enough time has",
				"passed since you hunted last time.",
				"You need rest.";
			next;
			mes "[Gem]",
				"Please come back ^0000FFafer dawn^000000",
				"tomorrow.";
			close;
			case 2:
			mes "[Gem]",
				"Adventurer, welcome back.";
			next;
			mes "[Gem]",
				"As usual, I'd like you to",
				"exterminate Restless Dead.",
				"There are three different kinds",
				"Small, Fast, and Big. Please",
				"exterminate 10 each.";
			setquest 14667;
			erasequest 14668;
			close;
			break;
		}
		
		mes "[Gem]",
			"Adventurer, are you busy?";
		next;
		mes "[Gem]",
			"Even if you are busy, please spare",
			"me a moment of your time.";
		next;
		if(select("Sure, why not?", "But I'm too busy.") == 2){
			mes "[Gem]",
				"Okay, then I'll wait until you have some time for me.";
			close;
		}
		
		mes "[Gem]",
			"As you know, we're here to keep an eye on them.";
		next;
		mes "["+strcharinfo(0)+"]",
			"Yes.";
		next;
		mes "[Gem]",
			"Now, that's interfering with our",
			"original mission, which is to keep",
			"this place clear of the unholy.";
		next;
		mes "[Gem]",
			"We've been trying to do both, and",
			"it's hard to do that between just",
			"the three of us.";
		next;
		mes "[Gem]",
			"The dead belong in the ground. We",
			"and here to put the undead back to",
			"eternal sleep.";
		next;
		mes "["+strcharinfo(0)+"]",
			"You mean you need help.";
		next;
		mes "[Gem]",
			"Yes, we do.";
		next;
		mes "["+strcharinfo(0)+"]",
			"What kinds of monsters do you want",
			"me to take care of?";
		next;
		mes "[Gem]",
			"Please exterminate ^0000FFRestless Dead^000000.",
			"There are ^0000FFthree different kinds",
			"Small, Fast, and Big. Please",
			"exterminate 10 each^000000.";
		next;
		mes "["+strcharinfo(0)+"]",
			"Got it. I was thinking, now that",
			"I'm here, I might as well help you",
			"while I can. I'm glad that I can.",
			"I'll be back.";
		
		setquest 14667;
		close;
	}
	
	end;
OnInit:
	questinfo 14658,QTYPE_QUEST,1;
	setquestinfo_req 14658,14656,1;
	questinfo 14666,QTYPE_QUEST,1;
	setquestinfo_req 14666,14665,1;
	
	questinfo 14667,QTYPE_QUEST,1;
	setquestinfo_req 14667,14666,2,14668,0;
end;

OnPCLoadMapEvent:
if(strcharinfo(3)=="gef_d01_i" && checkquest(14668,PLAYTIME)==2)
	showevent QTYPE_QUEST,1;
end;

OnPCLoginEvent:
if(illusion_vampire == 5){
	@illuvamp1talk = 0;
	@illuvamp2talk = 0;
	@illuvamp3talk = 0;
	@pirestilluvamptalk = 0;
}
end;
}

// =========================
//	Finding Jubilee
// =========================

gef_d01_i,150,224,5	script	Marina#illuvamp1	HIDDEN_WARP_NPC,12,12,{
	end;
	OnTouch:
	if(illusion_vampire == 5 && !@illuvamp1talk){
		@illuvamp1talk = 1;
		classchange 746,"Marina#illuvamp1",bc_self;
		sleep2 1250;
		npctalk "I'm sensing some faint energy in the east. Let's go.";
		sleep2 5250;
		specialeffect 304,SELF;
		classchange HIDDEN_WARP_NPC,"Marina#illuvamp1",bc_self;
	}
	end;
}

gef_d01_i,213,237,5	script	Marina#illuvamp2	HIDDEN_WARP_NPC,12,12,{
	end;
	OnTouch:
	if(illusion_vampire == 5 && !@illuvamp2talk){
		@illuvamp2talk = 1;
		classchange 746,"Marina#illuvamp2",bc_self;
		sleep2 1250;
		npctalk "I'm sensing faint energy in the south. Let's hurry.";
		sleep2 5250;
		specialeffect 304,SELF;
		classchange HIDDEN_WARP_NPC,"Marina#illuvamp2",bc_self;
	}
	end;
}

gef_d01_i,255,200,5	script	Marina#illuvamp3	HIDDEN_WARP_NPC,12,12,{
	end;
	OnTouch:
	if(illusion_vampire == 5 && !@illuvamp3talk){
		@illuvamp3talk = 1;
		classchange 746,"Marina#illuvamp3",bc_self;
		sleep2 1250;
		npctalk "Let's go south!";
		sleep2 5250;
		specialeffect 304,SELF;
		classchange HIDDEN_WARP_NPC,"Marina#illuvamp3",bc_self;
	}
	end;
}

gef_d01_i,254,162,1	script	Undead#illuvamp	HIDDEN_WARP_NPC,{ end; } //3752
gef_d01_i,252,160,1	script	Undead#illuvamp1	HIDDEN_WARP_NPC,{ end; } //3753
gef_d01_i,253,165,5	script	Marina#illuvamp4	HIDDEN_WARP_NPC,{ end; }

gef_d01_i,250,164,5	script	Priest#illuvamp	HIDDEN_WARP_NPC,12,12,{//110
	if(illusion_vampire != 5)
		end;
	
	setpcblock PCBLOCK_ALL, 1;
	addtimer 1000,strnpcinfo(0)+"::OnDeattach";
	mes "[Priest]",
		"What do I do? I can't walk because of my leg. I can't teleport because I don't have enough energy left.";
	next;
	emotion ET_CRY, getnpcid(0, "Priest#illuvamp");
	mes "[Priest]",
		"*Gasp* Am I going to die? Am I? I can't believe I'm going to die in a place like this!";
	next;
	classchange 3752,"Undead#illuvamp",bc_self;//TODO NPC
	npctalk "Grr...", "Undead#illuvamp",bc_self;
	classchange 3753,"Undead#illuvamp1",bc_self;//TODO NPC
	npctalk "Grrgghh...", "Undead#illuvamp1",bc_self;
	mes "[Priest]",
		"Aaa! Not again! Help!";
	next;
	select("A priest... Wait, is that him?");
	classchange 746,"Marina#illuvamp4",bc_self;
	npctalk "What are you doing here?","Marina#illuvamp4",bc_self;
	mes "["+strcharinfo(0)+"]",
		"Could he be Father Jubilee?",
		"Marina, I think we've found him!";
	next;
	mes "[Marina]",
		"Brother Jubilee?";
	next;
	npctalk "Let's secure this place first.","Marina#illuvamp4",bc_self;
	sleep2 1000;
	//npcskilleffect "MG_SAFETYWALL",0,250,164;
	specialeffect 315,SELF;
	sleep2 1500;
	npctalk "Adventurer?","Marina#illuvamp4",bc_self;
	mes "[Jubilee]",
		"Ah, Sister Marina! Help! You've got to help me if you don't want to feel guilt over my death later!";
	next;
	unittalk getcharid(3), strcharinfo(0) + " : Yes, I'm ready!",bc_self;
	mes "[Marina]",
		"The dead shall return to the earth!";
	next;
	npctalk "Turn undead!","Marina#illuvamp4",bc_self;
	sleep2 1000;
	npctalk "GRRRR!", "Undead#illuvamp",bc_self;
	npctalk "RAWR!", "Undead#illuvamp1",bc_self;		
	sleep2 2000;
	specialeffect 372,AREA,"Undead#illuvamp";
	specialeffect 372,AREA,"Undead#illuvamp1";
	sleep2 3250;
	classchange HIDDEN_WARP_NPC,"Undead#illuvamp",bc_self;
	classchange HIDDEN_WARP_NPC,"Undead#illuvamp1",bc_self;
	next;
	mes "[Marina]",
		"The dead shall return to the earth!";
	npctalk "Brother, are you all right?","Marina#illuvamp4",bc_self;
	sleep2 1500;
	npctalk "Whew, I am now. Thank you.","Priest#illuvamp",bc_self;
	next;
	mes "[Marina]",
		"What happened? Where's brother Jojo?";
	next;
	npctalk "*Shakes her head* Wizards.","Marina#illuvamp4",bc_self;
	mes "[Jubilee]",
		"He and I were checking this place when we found some fluorescent mushrooms. Brother Jojo's eyes gleamed and...";
	next;
	npctalk "What? A mushroom exploded? And?","Marina#illuvamp4",bc_self;
	mes "[Jubilee]",
		"He touched one of the mushrooms, and it exploded.";
	next;
	mes "[Jubilee]",
		"When I came back to my senses, he was gone and I couldn't move my leg.";
	next;
	mes "[Marina]",
		"Oh no, were you hit by the shrapnel?";
	next;
	mes "[Jubilee]",
		"Sister Marina, have you seen the mushrooms in this place? They're not like the mushrooms we know. They're miniature bombs that blow up when touched.";
	next;
	select("I'm glad they only grow here.");
	mes "[Marina]",
		"Brother Jubilee, do you think you can move?";
	next;
	mes "[Jubilee]",
		"If I could, I would've found my way back to you already.";
	next;
	select("I thought priests could heal themselves.");
	mes "[Jubilee]",
		"We take basic training to be servant of God, but what each one of us can do depends on our natural ability.";
	next;
	mes "[Jubilee]",
		"I specialize in singing. It's my purpose in life. I feel my greatest joy when I sing Odin's praises.";
	next;
	npctalk "I've been singing since I found Brother Jojo was missing.","Priest#illuvamp",bc_self;
	npctalk "You should've wasted your precious voice on these unholy creatures.","Marina#illuvamp4",bc_self;
	mes "[Marina]",
		"Don't be surprised. His singing voice really inspires courage and gives strength. He's here with us for a reason.";
	next;
	mes "[Marina]",
		"Adventurer, I'm going to take Brother Jubilee to Sister Gem. Could you take a look around this place? I'll be back as soon as I can.";
	next;
	mes "[Jubilee]",
		"Watch for illusions. The notebook's owner memories manifest themselves sporadically around here.";
	next;
	mes "[Jubilee]",
		"Also, I've sensed an evil presence. Please be careful.";
	next;
	mes "[Marina]",
		"Let's go.";
	close2;
	unittalk getcharid(3), strcharinfo(0) + " : I'd better look for Jojo.",bc_self;
	specialeffect 304,SELF;
	specialeffect 304,AREA,"Marina#illuvamp4";
	classchange HIDDEN_WARP_NPC,"Priest#illuvamp",bc_self;
	classchange HIDDEN_WARP_NPC,"Marina#illuvamp4",bc_self;
	completequest 14658;
	setquest 14657;
	setpcblock PCBLOCK_ALL, 0;
	illusion_vampire = 6;
	deltimer strnpcinfo(0)+"::OnDeattach";
	end;
OnDeattach:
	classchange HIDDEN_WARP_NPC,"Undead#illuvamp",bc_self;
	classchange HIDDEN_WARP_NPC,"Undead#illuvamp1",bc_self;
	classchange HIDDEN_WARP_NPC,"Marina#illuvamp4",bc_self;
	setpcblock PCBLOCK_ALL, 0;
	deltimer strnpcinfo(0)+"::OnDeattach";
end;
OnTouch:
	if(illusion_vampire == 5){
		classchange 110,"Priest#illuvamp",bc_self;
	}
end;
OnInit:
	questinfo 14657,QTYPE_QUEST;
	setquestinfo_req 14657,14658,1;
end;
}

// =========================
//	End Finding Jubilee
// =========================


// =========================
//	Finding Jojo
// =========================


// =========================
//	Fake Wizards
// =========================

gef_d01_i,156,234,4	script	Wizard#fake1inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 567,"Wizard#fake1",bc_self;
	}
end;
}

gef_d01_i,156,234,4	script	Wizard#fake1	HIDDEN_WARP_NPC,2,2,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "Hello. Are you an adventurer? How old are you? Is this you first time in this place?", "Wizard#fake1", bc_self;
		sleep2 1500;
		unittalk getcharid(3), strcharinfo(0) + " : This place is too dangerous for Novices like you. You'd better leave as soon as possible.",bc_self;
		sleep2 1500;
		npctalk "Do I look like a Novice? You're cute.", "Wizard#fake1", bc_self;
		sleep2 2625;
		unittalk getcharid(3), strcharinfo(0) + " : What's this?.",bc_self;
		sleep2 2625;
		setpcblock PCBLOCK_ALL, 0;
		classchange HIDDEN_WARP_NPC,"Wizard#fake1",bc_self;
	}
end;
}

gef_d01_i,233,236,5	script	Nightmare#fake	HIDDEN_WARP_NPC,{ end; }

gef_d01_i,236,235,4	script	Wizard#fake2inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 64,"Wizard#fake2",bc_self;
		//1061,1427,1964,3660,3661
		classchange 3661,"Nightmare#fake",bc_self;//TODO NPC
	}
end;
}

gef_d01_i,236,235,4	script	Wizard#fake2	HIDDEN_WARP_NPC,3,3,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "*Whine*", "Nightmare#fake", bc_self;
		sleep2 1500;
		npctalk "Ah, I'm sorry! Aww, this is just too creepy. Just kill me already. I can't watch the dreams you show me anymore.", "Wizard#fake2", bc_self;
		sleep2 2550;
		unittalk getcharid(3), strcharinfo(0) + " : This must be an old memory of the notebook's owner.",bc_self;
		sleep2 2050;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Nightmare#fake";
		sleep2 500;
		classchange HIDDEN_WARP_NPC,"Wizard#fake2",bc_self;
		classchange HIDDEN_WARP_NPC,"Nightmare#fake",bc_self;
	}
end;
}

gef_d01_i,254,200,4	script	Wizard#fake3inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 123,"Wizard#fake3",bc_self;
		classchange 673,"Wizard#fake4",bc_self;
		classchange 3753,"Undead#fake",bc_self;//TODO NPC
	}
end;
}

gef_d01_i,256,198,1	script	Undead#fake	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,254,200,5	script	Wizard#fake3	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,255,201,5	script	Wizard#fake4	HIDDEN_WARP_NPC,3,3,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		specialeffect 315,SELF;
		specialeffect 315,AREA,"Wizard#fake3";
		sleep2 1000;
		npctalk "Ah, What do we do? They're stronger than I thought.", "Wizard#fake4", bc_self;
		sleep2 2250;
		npctalk "When can we leave?", "Wizard#fake3", bc_self;
		sleep2 2250;
		npctalk "After they go away. They'll kill us if we move now.", "Wizard#fake4", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : This must be an old memory of the notebook's owner.",bc_self;
		sleep2 2750;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Wizard#fake3";
		specialeffect 496,AREA,"Undead#fake";
		sleep2 500;
		classchange HIDDEN_WARP_NPC,"Wizard#fake3",bc_self;
		classchange HIDDEN_WARP_NPC,"Wizard#fake4",bc_self;
		classchange HIDDEN_WARP_NPC,"Undead#fake",bc_self;
	}
end;
}

gef_d01_i,257,110,2	script	Wizard#fake5inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 10224,"Wizard#fake5",bc_self;
		classchange 3753,"Fast Undead#fake",bc_self;//TODO NPC
	}
end;
}

gef_d01_i,253,112,5	script	Fast Undead#fake	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,257,110,1	script	Wizard#fake5	HIDDEN_WARP_NPC,3,3,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "Why is that one fast? I might die before I have a chance to take a look at it.", "Wizard#fake5", bc_self;
		sleep2 2250;
		specialeffect 95,AREA,"Fast Undead#fake";
		npctalk "How can I catch it? I wish there was a way to take it to my lab...", "Wizard#fake5", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2500;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Fast Undead#fake";
		sleep2 500;
		classchange HIDDEN_WARP_NPC,"Wizard#fake5",bc_self;
		classchange HIDDEN_WARP_NPC,"Fast Undead#fake",bc_self;
	}
end;
}

gef_d01_i,228,74,4	script	Shining Mushroom#fake	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,230,76,2	script	Wizard#fake6inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 704,"Wizard#fake6",bc_self;
		classchange 3755,"Shining Mushroom#fake",bc_self;//TODO NPC
	}
end;
}

gef_d01_i,230,76,4	script	Wizard#fake6	HIDDEN_WARP_NPC,3,3,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "I'd better be careful. I don't want to die because I was gathering some mushroom spores.", "Wizard#fake6", bc_self;
		sleep2 2250;
		specialeffect 500,AREA,"Shining Mushroom#fake";
		npctalk "This should be enough to illuminate a room.", "Wizard#fake6", bc_self;
		sleep2 2550;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2450;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Shining Mushroom#fake";
		sleep2 550;
		classchange HIDDEN_WARP_NPC,"Wizard#fake6",bc_self;
		classchange HIDDEN_WARP_NPC,"Shining Mushroom#fake",bc_self;
	}
end;
}

gef_d01_i,136,58,4	script	Nameless Catacomb#fake	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,137,60,2	script	Wizard#fake7inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 64,"Wizard#fake7",bc_self;
		classchange 557,"Nameless Catacomb#fake",bc_self;//TODO NPC
	}
end;
}

gef_d01_i,137,60,4	script	Wizard#fake7	HIDDEN_WARP_NPC,3,3,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		specialeffect 611,AREA,"Nameless Catacomb#fake";
		npctalk "Um, even this can't raise the dead. Then what brought those creatures back from the dead?", "Wizard#fake7", bc_self;
		sleep2 2350;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2350;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Nameless Catacomb#fake";
		sleep2 550;
		classchange HIDDEN_WARP_NPC,"Wizard#fake7",bc_self;
		classchange HIDDEN_WARP_NPC,"Nameless Catacomb#fake",bc_self;
	}
end;
}

gef_d01_i,50,254,4	script	Nameless Catacomb#fake1	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,50,257,2	script	Wizard#fake8inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 123,"Wizard#fake8",bc_self;
		classchange 64,"Wizard#fake9",bc_self;
		classchange 557,"Nameless Catacomb#fake1",bc_self;//TODO NPC
	}
end;
}

gef_d01_i,47,254,5	script	Wizard#fake9	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,50,257,5	script	Wizard#fake8	HIDDEN_WARP_NPC,3,3,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		emotion ET_THINK, getnpcid(0, "Nameless Catacomb#fake1");
		sleep2 1000;
		specialeffect 386,AREA,"Nameless Catacomb#fake1";
		npctalk "Nothing happened. I'll increase the amount of holy water for the forty-ninth attempt.", "Wizard#fake9", bc_self;
		sleep2 2250;
		npctalk "Wouldn't it be better if we let a priest handle this?", "Wizard#fake8", bc_self;
		sleep2 2250;
		npctalk "No. Priests will try to get rid of these. Just focus on recording this process.", "Wizard#fake9", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2250;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Wizard#fake9";
		specialeffect 496,AREA,"Nameless Catacomb#fake1";
		sleep2 550;
		classchange HIDDEN_WARP_NPC,"Wizard#fake8",bc_self;
		classchange HIDDEN_WARP_NPC,"Wizard#fake9",bc_self;
		classchange HIDDEN_WARP_NPC,"Nameless Catacomb#fake1",bc_self;
	}
end;
}

gef_d01_i,53,166,2	script	Wizard#fake10inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 937,"Wizard#fake11",bc_self;
		classchange 123,"Wizard#fake10",bc_self;
	}
end;
}

gef_d01_i,55,167,4	script	Wizard#fake11	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,53,166,4	script	Wizard#fake10	HIDDEN_WARP_NPC,3,3,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "I miss my Happy. When we finally make this work, I want to bring back Happy first.", "Wizard#fake11", bc_self;
		sleep2 2250;
		npctalk "Don't look at them. They're not normal. Happy will probably chew on you instead of his chew toy.", "Wizard#fake10", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2250;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Wizard#fake11";
		sleep2 550;
		classchange HIDDEN_WARP_NPC,"Wizard#fake10",bc_self;
		classchange HIDDEN_WARP_NPC,"Wizard#fake11",bc_self;
	}
end;
}

gef_d01_i,209,146,2	script	Wizard#fake12inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 937,"Wizard#fake13",bc_self;
		classchange 673,"Wizard#fake12",bc_self;
		classchange 3752,"Undead#fake4",bc_self;
		classchange 3753,"Undead#fake5",bc_self;
		classchange 3753,"Undead#fake6",bc_self;
	}
end;
}

gef_d01_i,207,152,5	script	Undead#fake4	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,205,151,5	script	Undead#fake5	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,209,151,4	script	Undead#fake6	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,207,149,5	script	Wizard#fake13	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,209,146,1	script	Wizard#fake12	HIDDEN_WARP_NPC,4,4,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		emotion ET_HUK, getnpcid(0, "Wizard#fake12");
		npctalk "Hey, there are too many of them. I told you to lure just one not this many!", "Wizard#fake12", bc_self;
		sleep2 2250;
		emotion ET_HELP, getnpcid(0, "Wizard#fake13");
		npctalk "I can't stop them from following me!", "Wizard#fake13", bc_self;
		sleep2 2250;
		npctalk "Get down!", "Wizard#fake12", bc_self;
		specialeffect 722,AREA,"Undead#fake4";//901, 941
		specialeffect 722,AREA,"Undead#fake5";
		specialeffect 722,AREA,"Undead#fake6";
		sleep2 1500;
		classchange HIDDEN_WARP_NPC,"Undead#fake4",bc_self;
		classchange HIDDEN_WARP_NPC,"Undead#fake5",bc_self;
		classchange HIDDEN_WARP_NPC,"Undead#fake6",bc_self;
		npctalk "Whew, thanks!", "Wizard#fake13", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2250;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Wizard#fake13";
		sleep2 550;
		classchange HIDDEN_WARP_NPC,"Wizard#fake12",bc_self;
		classchange HIDDEN_WARP_NPC,"Wizard#fake13",bc_self;
	}
end;
}

gef_d01_i,93,34,2	script	Wizard#fake14inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 10224,"Wizard#fake14",bc_self;
		classchange 64,"Wizard#fake15",bc_self;
		classchange 3753,"Undead#fake7",bc_self;
	}
end;
}
gef_d01_i,91,35,5	script	Undead#fake7	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,94,37,3	script	Wizard#fake15	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,93,34,1	script	Wizard#fake14	HIDDEN_WARP_NPC,4,4,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "Let's use a scroll and a Yggdrasil leaf at the same time this time. I'll activate the scroll from here. You use the leaf form there.", "Wizard#fake14", bc_self;
		sleep2 2250;
		npctalk "Okay.", "Wizard#fake15", bc_self;
		sleep2 2250;
		npctalk "Did we fail again?", "Wizard#fake14", bc_self;
		sleep2 2250;
		npctalk "Why wouldn't it turn into a human? If the dead can come back to life, then it should be able to turn into a human.", "Wizard#fake15", bc_self;
		sleep2 2250;
		npctalk "Let's calm down, and try something else.", "Wizard#fake14", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2250;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Wizard#fake15";
		specialeffect 496,AREA,"Undead#fake7";
		sleep2 550;
		classchange HIDDEN_WARP_NPC,"Wizard#fake14",bc_self;
		classchange HIDDEN_WARP_NPC,"Wizard#fake15",bc_self;
		classchange HIDDEN_WARP_NPC,"Undead#fake7",bc_self;
	}
end;
}

gef_d01_i,46,112,2	script	Wizard#fake16inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 937,"Wizard#fake16",bc_self;
		classchange 669,"Wizard#fake17",bc_self;
		classchange 3753,"Undead#fake8",bc_self;
	}
end;
}
gef_d01_i,47,110,7	script	Undead#fake8	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,49,113,4	script	Wizard#fake17	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,46,112,5	script	Wizard#fake16	HIDDEN_WARP_NPC,4,4,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "Ah, it died !", "Wizard#fake17", bc_self;
		sleep2 2250;
		npctalk "Maybe Yggdrasil leaves kill the undead.", "Wizard#fake16", bc_self;
		sleep2 2250;
		npctalk "I think so. This means we can use them to take care of the undead.", "Wizard#fake17", bc_self;
		sleep2 2250;
		npctalk "You're a genius!.", "Wizard#fake16", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2250;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Wizard#fake17";
		specialeffect 496,AREA,"Undead#fake8";
		sleep2 550;
		classchange HIDDEN_WARP_NPC,"Wizard#fake16",bc_self;
		classchange HIDDEN_WARP_NPC,"Wizard#fake17",bc_self;
		classchange HIDDEN_WARP_NPC,"Undead#fake8",bc_self;
	}
end;
}

gef_d01_i,67,83,2	script	Wizard#fake18inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 673,"Wizard#fake18",bc_self;
		classchange 735,"Wizard#fake19",bc_self;
	}
end;
}
gef_d01_i,67,85,5	script	Wizard#fake19	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,67,83,1	script	Wizard#fake18	HIDDEN_WARP_NPC,4,4,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "Maybe I should crush and mix these gemstones together, and see if I can use the mixture to separate the souls of the undead from their bodies.", "Wizard#fake19", bc_self;
		sleep2 2250;
		npctalk "I don't think those zombies have souls.", "Wizard#fake18", bc_self;
		sleep2 2250;
		npctalk "Then what can explain their mobility? Every living thing that moves has a soul.", "Wizard#fake19", bc_self;
		sleep2 2250;
		npctalk "Muscle spasm?", "Wizard#fake18", bc_self;
		sleep2 2250;
		npctalk "No. It's clear their souls have returned to their dead bodies. If we can attach and detach our souls freely from our bodies, we can forever escape from physical pain!", "Wizard#fake19", bc_self;
		sleep2 2250;
		npctalk "But our bodies don't need souls for their survival. I still think those corpses are just?", "Wizard#fake18", bc_self;
		sleep2 2250;
		npctalk "Just stop talking, and take care of these.", "Wizard#fake19", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2250;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Wizard#fake19";
		sleep2 550;
		classchange HIDDEN_WARP_NPC,"Wizard#fake18",bc_self;
		classchange HIDDEN_WARP_NPC,"Wizard#fake19",bc_self;
	}
end;
}

gef_d01_i,101,124,2	script	Wizard#fake20inv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire == 6){
		classchange 10224,"Wizard#fake20",bc_self;
		classchange 10224,"Wizard#fake21",bc_self;
	}
end;
}
gef_d01_i,99,122,7	script	Wizard#fake21	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,101,124,3	script	Wizard#fake20	HIDDEN_WARP_NPC,4,4,{
end;
OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "We can't experiment in a place like this. Why don't we capture one a bring it to our lab?", "Wizard#fake20", bc_self;
		sleep2 2250;
		npctalk "Don't you feel the energy in the air?", "Wizard#fake21", bc_self;
		sleep2 2250;
		npctalk "What are you saying?", "Wizard#fake20", bc_self;
		sleep2 2250;
		npctalk "Imagine what we can do with this power.", "Wizard#fake21", bc_self;
		sleep2 2250;
		npctalk "...Oh, you're right.", "Wizard#fake20", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : This... It must be an old memory of the notebook's owner.",bc_self;
		sleep2 2250;
		setpcblock PCBLOCK_ALL, 0;
		specialeffect 496,SELF;
		specialeffect 496,AREA,"Wizard#fake21";
		sleep2 550;
		classchange HIDDEN_WARP_NPC,"Wizard#fake20",bc_self;
		classchange HIDDEN_WARP_NPC,"Wizard#fake21",bc_self;
	}
end;
}

// =========================
//	End Fake Wizards
// =========================

// =========================
//	Found Bomi
// =========================

gef_d01_i,81,135,2	script	Wizard#illuvampinv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire > 5){
		if(!$illuvamp_bomiSpawned || illusion_vampire != 14)
			classchange 10224,"Wizard#illuvamp",bc_self;
		classchange 3970,"Mushroom#illuvamp",bc_self;//TODO NPC 1084
	}
	if(illusion_vampire == 10 || illusion_vampire == 11){
		classchange 746,"Marina#illuvamp5",bc_self;
		classchange 669,"Antoine#illuvamp5",bc_self;
		classchange 79,"Gem#illuvamp5",bc_self;
		if(illusion_vampire == 11){
			classchange 4_DRACULA,"Dracula#illuvamp5",bc_self;
			classchange 735,"Jojo#illuvamp5",bc_self;
			classchange 4_NFBAT,"King#illuvamp5",bc_self;
		}
	}
end;
}

gef_d01_i,86,133,2	script	Marina#illuvamp5	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,85,139,4	script	Antoine#illuvamp5	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,80,139,5	script	Gem#illuvamp5	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,82,132,4	script	Mushroom#illuvamp	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,86,132,2	script	Dracula#illuvamp	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,84,135,3	script	Dracula#illuvamp5	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,80,132,0	script	Jojo#illuvamp5	HIDDEN_WARP_NPC,{ end; }
gef_d01_i,87,136,4	script	King#illuvamp5	HIDDEN_WARP_NPC,{ end; }

// BOMI HERE
gef_d01_i,81,135,5	script	Wizard#illuvamp	HIDDEN_WARP_NPC,3,3,{
if(illusion_vampire == 6){
	setpcblock PCBLOCK_ALL, 1;
	mes "[Wizard]",
		"This one has a different color from Illusion Black Mushrooms. Is it a new kind? I'd better pick it carefully..";
	next;
	mes "["+strcharinfo(0)+"]",
		"^0000FFA wizard^000000... Could that be ^0000FFJojo^000000?";
	next;
	select("Jojo?");
	mes "[Wizard]",
		"Are you a human?";
	next;
	mes "["+strcharinfo(0)+"]",
		"Jojo? You're Jojo, right? Your colleagues are worried about you. Let's go back. You're not hurt, are you?";
	next;
	mes "[Wizard]",
		"No, I'm not Jojo.";
	next;
	mes "[Wizard]",
		"Do I... look like a human?";
	next;
	mes "["+strcharinfo(0)+"]",
		"Of course.";
	next;
	mes "[Wizard]",
		"...";
	next;
	select("...Are you not a human?");
	emotion ET_HUK,playerattached();
	mes "[Wizard]",
		"I'm... My name is ^0000FFBomi^000000. I'm sorry I'm not the person you're looking for.";
	next;
	mes "["+strcharinfo(0)+"]",
		"Bomi? Wait, you're that Bomi?";
	next;
	mes "[Bomi]",
		"Do you know me?";
	next;
	select("I've picked up your notebook.");
	mes "["+strcharinfo(0)+"]",
		"I didn't mean to be nosy. I had to know who it belonged to.";
	next;
	mes "[Bomi]",
		"I threw it away.";
	next;
	mes "["+strcharinfo(0)+"]",
		"Why did you throw it away? Why are you staying here?";
	next;
	mes "[Bomi]",
		"Because I'm a monster. I belong here.";
	next;
	select("Why do you think you're a monster?");
	mes "[Bomi]",
		"Because I'm a vampire.";
	next;
	select("A vampire?!");
	mes "["+strcharinfo(0)+"]",
		"What happened? You were a human.";
	next;
	mes "[Bomi]",
		"I was betrayed by my best friend.";
	unittalk getcharid(3), strcharinfo(0) + " : ...You were betrayed?",bc_self;
	next;
	mes "[Bomi]",
		"Most people try to make the most out of life because they know they can't live forever.";
	next;
	mes "[Bomi]",
		"I was given a shorter time to live than most. Ever since I was born, I'd been told I'd never outlive my parents.";
	next;
	mes "[Bomi]",
		"People desire what they don't have. I desired ^0000FFstrength^000000 because I was too small and frail to live like others my age.";
	next;
	mes "[Bomi]",
		"I became a wizard because I thought magic could compensate for my physical weakness.";
	next;
	mes "[Bomi]",
		"I didn't realize a strong mind cames from a strong body, though...";
	next;
	mes "[Bomi]",
		"Magic was exhausting to both my mind and my body. I reached my limits more quickly than I thought. But I wasn't upset. I thought I could remedy that.";
	unittalk getcharid(3), strcharinfo(0) + " : Oh. That's why you were studying the zombies in these catacombs.",bc_self;
	next;
	mes "[Bomi]",
		"Yes. Doing that, I felt more alive than ever. My burning desire for life made me who I was.";
	next;
	mes "[Bomi]",
		"Then, one day, while I was here, I met an ^0000FFentity^000000 who was not human.";
	next;
	mes "Bomi is gathering her thoughts. I should talk to her later.";
	//give quest
	setpcblock PCBLOCK_ALL, 0;
	completequest 14657;
	setquest 14659;
	illusion_vampire = 7;
	close;
}

if(illusion_vampire == 7){
	setpcblock PCBLOCK_ALL, 1;
	sleep2 1000;
	npctalk "Do you know what I found here?", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	unittalk getcharid(3), strcharinfo(0) + " : Nightmares, mushrooms, zombies...",bc_self;
	sleep2 2250;
	npctalk "There's one more..", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	unittalk getcharid(3), strcharinfo(0) + " : Are you talking about Dracula? I've heard of him.",bc_self;
	sleep2 2250;
	npctalk "When I first met him, he was close to perishing. His vulnerability reminded me strongly of my own.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "That's why I fed him my blood and tended his wounds, even though I know I shouldn't.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "Later, I met him again and we got close. He was my first real friend.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	classchange 4_DRACULA,"Dracula#illuvamp",bc_self;//TODO NPC 1084
	sleep2 500;
	specialeffect 496,AREA,"Dracula#illuvamp";
	npctalk "Why did you save me?", "Dracula#illuvamp", bc_self;
	sleep2 2250;
	npctalk "It's hard to explain. Let's just say we humans like to save others.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "That's not true. Others of your kind just want to kill me.", "Dracula#illuvamp", bc_self;
	sleep2 2250;
	npctalk "Not all of us are made the same.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "How about I give you a gift in return for your favor? I know you want a strong body and longevity.", "Dracula#illuvamp", bc_self;
	sleep2 2250;
	npctalk "But how? Wait, are you offering...? No, thanks.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "You want them so badly that you're risking your life by studying in a place like this.", "Dracula#illuvamp", bc_self;
	sleep2 2250;
	npctalk "I do, but I don't want to give up my humanity for them.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "But you're afraid of dying. And your days are numbered.", "Dracula#illuvamp", bc_self;
	sleep2 2250;
	npctalk "My fear of death is what keeps me going. It's made me who I am.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "Giving up my humanity for eternal life goes against my beliefs, all my hard work up till now, and everying I tried hard to protect.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "Above all, I'll be giving up on myself, and I can't do that.", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "Even if you're turned, you'll still be you.", "Dracula#illuvamp", bc_self;
	sleep2 2250;
	npctalk "On the outside, maybe. But I will no longer fear death, and therefore have no desire to live..", "Wizard#illuvamp", bc_self;
	sleep2 2250;
	npctalk "It pains me to see you wither away, day by day.", "Dracula#illuvamp", bc_self;
	sleep2 2250;
	npctalk "I can't say I understand your logic, but I'll respect your wishes.", "Dracula#illuvamp", bc_self;
	sleep2 2250;
	mes "[Bomi]",
		"So he ^0000FFpromised^000000. Then one day, some people came here looking for him, and they fought.";
	next;
	mes "[Bomi]",
		"And the next thing I know, I was turned. Dracula broke his promise.";
	next;
	npctalk "How could you do this to me?!", "Wizard#illuvamp", bc_self;
	sleep2 1000;
	npctalk "I'm sorry..", "Dracula#illuvamp", bc_self;
	sleep2 4500;
	specialeffect 496,AREA,"Dracula#illuvamp";
	sleep2 550;
	classchange HIDDEN_WARP_NPC,"Dracula#illuvamp",bc_self;
	mes "[Bomi]",
		"I couldn't belive he turned me into a monster. I trusted him!";
	next;
	mes "[Bomi]",
		"People in the outside world must think I skipped town. How long has it been since I left?";
	next;
	mes "[Bomi]",
		"I try to ignore my reality, but this ever-present hunger and thirst keep reminding me what kind of terrible monster I am.";
	next;
	mes "[Bomi]",
		"If I go back to the outside world, I won't be able to stop myself from hurting people.";
	next;
	select("How did you sustain yourself so far?");
	mes "[Bomi]",
		"I studied pharmaceutical formulation to make up for my weak stamina with potions.";
	next;
	mes "[Bomi]",
		"I drink fake blood that I make with the ingredients I can find here. I may look human enough, but I'm not. Not really.";
	next;
	mes "[Bomi]",
		"I'm sorry I bored you with my story.";
	next;
	mes "["+strcharinfo(0)+"]",
		"Not at all.";
	next;
	mes "[Bomi]",
		"Adventurer, I don't want to impose on your kindness, but may I ask you a favor?";
	next;
	select("Sure, anything for you.");
	mes "[Bomi]",
		"You shouldn't say that. What if I ask for your blood?";
	emotion ET_SWEAT, playerattached();
	next;
	mes "[Bomi]",
		"I was joking. I'm in the middle of collecting the fake blood ingredients, but right now I want to examine this mushroom. I've never seen it before. I want to check it while it's till fresh.";
	next;
	mes "["+strcharinfo(0)+"]",
		"What kinds of ingredients do you need? I'll get them for you.";
	next;
	mes "[Bomi]",
		"Thank you. I need ^0000FF10 Sticky Bloods from Matte Drainliars and 10 Mushroom Saps from Illusion Black Mushrooms^000000. Thank you for doing this for me.";
	
	setpcblock PCBLOCK_ALL, 0;
	// give quest
	completequest 14659;
	setquest 14660;
	illusion_vampire = 8;
	close;
}

if(illusion_vampire == 8){
	setpcblock PCBLOCK_ALL, 1;
	mes "["+strcharinfo(0)+"]",
		"Here, I brought the things you asked.";
	next;
	mes "[Bomi]",
		"Let's see...";
	next;
	if(checkquest(14660,HUNTING) != 2 || 10 > countitem(25269) || 10 > countitem(25268)){
		mes "[Bomi]",
			"This isn't enough.";
		next;
		mes "[Bomi]",
			"I need ^0000FF10 Sticky Bloods from Matte Drainliars and 10 Mushroom Saps from Illusion Black Mushrooms^000000. Thank you for doing this for me.";
		setpcblock PCBLOCK_ALL, 0;
		close;
	}
	mes "[Bomi]",
		"Thank you.";
	next;
	mes "["+strcharinfo(0)+"]",
		"How's the mushroom?";
	next;
	mes "[Bomi]",
		"It turned out to be and ordinary, invaluable mushroom.";
	next;
	select("How do you make artificial blood?");
	mes "[Bomi]",
		"Matte Drainliars feed on the blood of the reanimated corpses in this place.";
	next;
	mes "[Bomi]",
		"Did you get it? But their blood is highly toxic. So I use these mushrooms to detoxify it.";
	next;
	specialeffect 305,SELF;
	mes "[Bomi]",
		"Like this!";
	next;
	mes "[Bomi]",
		"But even their sap cannot completely remove the toxins in the blood. And when I ingest too much toxins...";
	next;
	select("Maybe you should've chosen a different career.");
	mes "["+strcharinfo(0)+"]",
		"Like alchemist, for example.";
	next;
	mes "[Bomi]",
		"I didn't know I was talented at this. If I had ^0000FFenough time to live^000000, I would've had many different experiences. I might have chosen a different path.";
	next;
	mes "[Bomi]",
		"Oh, by the way, weren't you looking for someone? What did you say his name was? Juju?";
	next;
	select("Jojo.");
	mes "[Bomi]",
		"I haven't seen any other humans around here, but if I do, I'll let him know you're looking for him.";
	next;
	mes "[Bomi]",
		"I hope you'll find him soon. I'm not the only one here, you know. If you haven't found him, maybe he's?";
	next;
	mes "[Bomi]",
		"Never mind. Good luck finding him. Maybe you should check the catacombs in the south.";
	next;
	mes "["+strcharinfo(0)+"]",
		"Thank you. I'll see you.";
	next;
	mes "[Bomi]",
		"You'd better hurry.";
	//give quest
	delitem 25269,10;
	delitem 25268,10;
	setpcblock PCBLOCK_ALL, 0;
	illusion_vampire = 9;
	completequest 14660;
	setquest 14661;
	viewpoint 1,189,98,1,0xFF0000;//shoud be pink/purple
	close;
}

if(illusion_vampire == 9 && checkquest(14661) == 1){
	mes "[Bomi]",
		"You'd better hurry and check the catacombs in the south.";
	viewpoint 1,189,98,1,0xFF0000;//shoud be pink/purple
	close;
}

if(illusion_vampire == 10){
	setpcblock PCBLOCK_ALL, 1;
	mes "[Bomi]",
		"Stay away from me, and I won't hurt you.";
	next;
	mes "[Marina]",
		"One of us is missing. You hurt him, didn't you?";
	next;
	mes "[Bomi]",
		"I've never hurt anyone, and I won't start now.";
	next;
	mes "[Marina]",
		"Even if you won't, we're not going to let you go! Your existence in itself goes against His will!";
	next;
	mes "[Bomi]",
		"His will? God loves us all. Isn't that what you preach?";
	next;
	mes "[Marina]",
		"The dead belong in the ground, and you're on of them. What do you think you are?";
	next;
	mes "[Bomi]",
		"...But... But I really didn't hurt anyone.";
	next;
	mes "[Marina]",
		"That doesn't guarantee you won't in the future.";
	next;
	mes "[Gem]",
		"Wait, Sister Marina. Calm yourself.";
	next;
	mes "[Marina]",
		"Why aren't we getting rid of her already? The dead shall return to the earth! Brother Antoine!";
	npctalk "Sigh, Sister Marina is right.","Antoine#illuvamp5",bc_self;
	sleep2 2000;
	npctalk "Guillotine Fist!.","Marina#illuvamp5",bc_self;
	sleep2 2000;
	classchange 4_DRACULA,"Dracula#illuvamp5",bc_self;
	sleep2 100;
	specialeffect 669,AREA,"Dracula#illuvamp5";
	specialeffect 670,AREA,"Dracula#illuvamp5";
	specialeffect 510,AREA,"Dracula#illuvamp5";
	specialeffect 888,AREA,"Dracula#illuvamp5";
	npctalk "Ugh!","Dracula#illuvamp5",bc_self;
	next;
	classchange 4_NFBAT,"King#illuvamp5",bc_self;
	specialeffect 583,AREA,"King#illuvamp5";
	emotion ET_ANGER,getnpcid(0,"King#illuvamp5");
	mes "[King]",
		"Argh, I can't believe you threw yourself in the middle of that! This is why I can't leave you alone!";
	next;
	mes "[Bomi]",
		"...Dracula? Why?";
	next;
	mes "[Marina]",
		"There's another vampire! No wonder why this place felt so off? It's filled with vampires!";
	npctalk "Hey, you bat, the one over there! Are you also a vampire?","Marina#illuvamp5",bc_self;
	sleep2 2000;
	npctalk "Did the vampire call for help?","Antoine#illuvamp5",bc_self;
	next;
	emotion ET_FRET,getnpcid(0,"King#illuvamp5");
	mes "[King]",
		"Human, did you just call me a bat? How dare you?";
	next;
	mes "[Gem]",
		"Wait, Sister Marina. I said, calm yourself.";
	next;
	mes "[Marina]",
		"We have to act now. We've already incapacitated one out of the three.";
	next;
	mes "[Gem]",
		"But one of them doesn't want to fight. She wants to talk.";
	next;
	//King, explode 9999dmg
	specialeffect EF_SUI_EXPLOSION,AREA,"Marina#illuvamp5";
	mes "[King]",
		"Who wants to talk? Because I don't! I'm not going to go down without a fight!";
	next;
	mes "[Marina]",
		"Grr, let me go! Enough is enough!";
	next;
	classchange 735,"Jojo#illuvamp5",bc_self;
	specialeffect 304,AREA,"Jojo#illuvamp5";
	emotion ET_CONFUSE,getnpcid(0,"Jojo#illuvamp5");
	mes "[Jojo]",
		"Oh geez, how do you move so fast?";
	next;
	mes "[Jojo]",
		"Everyone, calm the hell down!";
	next;
	mes "[Gem]",
		"Brother Jojo! You're safe!";
	next;
	mes "[Marina]",
		"Where were you? We couldn't find you, and we looked everywhere!";
	next;
	mes "[Antoine]",
		"It's true. His wounds are almost fully healed.";
	next;
	mes "[Dracula]",
		"Don't touch Bomi... She... I... We don't want to hurt anyone... She's taught me that...";
	npctalk "Hampf, you should worry about yourself? You're dying!","King#illuvamp5",bc_self;
	next;
	mes "[Bomi]",
		"Dracula! Dracula! Let me heal you!";
	next;
	mes "[Marina]",
		"I'm not going to let you do that!";
	next;
	mes "[Gem]",
		"Leave them be. They saved Jojo.";
	next;
	mes "[Marina]",
		"But they could be using him as bait!";
	next;
	mes "[Gem]",
		"Even if they attack us, there are more of us than them.";
	npctalk "You're delusinal if you think there's no strength in numbers","King#illuvamp5",bc_self;
	next;
	mes "[Antoine]",
		"I agree with Sister Gem. Also, it's not an everyday opportunity that we can see vampires this close.";
	next;
	mes "[Gem]",
		"You're Bomi, right? I read your notebook. What happened? What did these vampires do to you?";
	next;
	select("I can explain");
	mes "I relayed Bomi and Dracula's story to Nun Gem and ther others.";
	next;
	mes "[Gem]",
		"So you're saying they really are innocent.";
	next;
	mes "[Bomi]",
		"Dracula, hang on. Drink this.";
	next;
	mes "[Marina]",
		"Whose blood is that? You can't let him drink that!";
	next;
	mes "[Bomi]",
		"It's not real blood! He needs it! Can't you see he's dying?";
	next;
	mes "[Marina]",
		"You're dead already!";
	next;
	mes "[King]",
		"Gosh, you're so stubborn. Feed him. I'll keep them at bay.";
	npctalk "Let me help.","Jojo#illuvamp5",bc_self;
	sleep2 1000;
	npctalk "You may feed him.","Gem#illuvamp5",bc_self;
	next;
	mes "[Marina]",
		"You're letting her feed him, that vampire? Sister Gem, have you forgotten your duty as our leader?";
	next;
	mes "[Jojo]",
		"Marina, I don't care who they are. They saved me and asked for nothing in return.";
	next;
	mes "[Jojo]",
		"I didn't understand why vampires would help humans, but now I know. Dracula learned from Bomi how to be more human.";
	next;
	mes "[Jojo]",
		"He said he wanted to understand humans, so he could better understand her. And I think he's achieved his goal.";
	next;
	mes "[Jojo]",
		"He helped me and expected nothing in return. Such a random act of kindness is a human trait, isn't it?";
	next;
	mes "[Jojo]",
		"And you shouldn't help someone because of who they are. Marina, are you really going to let him die because he's not one of us?";
	next;
	mes "[Marina]",
		"That only applies to us humans. They're vampires!";
	next;
	mes "[King]",
		"Now I understand why Dracula was so distrustful of you humans. I thought he was being too picky.";
	next;
	mes "[King]",
		"Hey, you monk, over there. What do think makes you human? What do you think makes a vampire a vampire? What if there's a vampirethat's never hurt anyone in their life?";
	next;
	mes "[Marina]",
		"I'll get rid of them.";
	next;
	mes "[King]",
		"What if there's a human who did nothing but hurt others. What would you do about them?";
	next;
	mes "[Marina]",
		"I'll let justice decide their fate.";
	next;
	mes "[King]",
		"When I hunt, I treated all humans equally because I'm a vampire. That's my rule.";
	next;
	mes "[King]",
		"Their rule is to help anyone who needs help regardless of who they are. Simple, isn't it?";
	next;
	mes "[Marina]",
		"...";
	next;
	mes "[Dracula]",
		"Mm... Bomi?";
	npctalk "Dracula, how are you feeling?","King#illuvamp5",bc_self;
	sleep2 1000;
	npctalk "Whew, he's out of the woods now.","Jojo#illuvamp5",bc_self;
	next;
	mes "[Dracula]",
		"Did you... save me? I thought you wanted me to die.";
	next;
	mes "[Bomi]",
		"No, and now I understand why you made that decision. You couldn't just let me die, could you?";
	next;
	mes "[Bomi]",
		"Because I couldn't do it, either.";
	next;
	mes "[Dracula]",
		"...";
	npctalk "What are you guys doing?","King#illuvamp5",bc_self;
	sleep2 2000;
	npctalk "Leave them alone. They're reconiling with each other.",bc_self;
	next;
	mes "[Gem]",
		"Brothers. Sisters. We need to talk.";
	//give quest
	setpcblock PCBLOCK_ALL, 0;
	completequest 14663;
	setquest 14664;
	illusion_vampire = 11;
	close;
}

if(illusion_vampire == 11){
	setpcblock PCBLOCK_ALL, 1;
	mes "[Bomi]",
		"Thank you, and I'm sorry.";
	next;
	mes "[Dracula]",
		"I'm sorry I broke my promise. But even if I could go back in time, I would do it again.";
	next;
	mes "[Bomi]",
		"I understand now why you did that.";
	next;
	mes "[Jojo]",
		"Did you guys make up? Dracula, the worst is over. You just need to rest and regain your energy.";
	next;
	mes "[Dracula]",
		"Thank you.";
	next;
	mes "[King]",
		"*Snort* You can't beat mushrooms, but you can save vampires.";
	npctalk "They weren't mushrooms? They were zombies!","Jojo#illuvamp5",bc_self;
	sleep2 1500;
	npctalk "Mushrooms and zombies. Same difference to me.","King#illuvamp5",bc_self;
	next;
	mes "[King]",
		"Drac, let's go. I know you're not hurting anymore. We should really go back to our castle this time.";
	emotion ET_GO,getnpcid(0,"King#illuvamp5");
	next;
	mes "[Dracula]",
		"I'm going to stay.";
	next;
	mes "[King]",
		"What? No! You've made up with her. It's time to leave!";
	next;
	mes "[Gem]",
		"Please hear me out.";
	npctalk "What more do you have to say?","King#illuvamp5",bc_self;
	sleep2 1500;
	npctalk "Just listen, will you?","Jojo#illuvamp5",bc_self;
	next;
	mes "[Gem]",
		"We know you haven't hurt anyone, and you want to keep it that way. And we appreciate you saved Brother Jojo.";
	npctalk "And?","King#illuvamp5",bc_self;
	sleep2 1500;
	npctalk "Just hush!","Jojo#illuvamp5",bc_self;
	next;
	mes "[Gem]",
		"But that doesn't change the fact that your existence in itself defies your god's will. We can't leave you alone.";
	next;
	mes "[King]",
		"Drac, they won't leave us alone.",
		"Let's just get rid of them!";
	emotion ET_ANGER,getnpcid(0,"King#illuvamp5");
	npctalk "No!","Wizard#illuvamp",bc_self;
	sleep2 1000;
	npctalk "No!","Dracula#illuvamp5",bc_self;
	next;
	mes "[Marina]",
		"Sister Gem, this is just a waste of time. They're going to kill us the first chance they get. Let's get rid of them before they do!";
	next;
	mes "[Antoine]",
		"Sisters, let me talk. Your tendency to jump to conclusions is not helping this situation.";
	next;
	mes "[Antoine]",
		"We understand you don't want to hurt anyone.";
	next;
	mes "[Antoine]",
		"But you're dangerous to others, whether you like it or not.";
	next;
	mes "[King]",
		"Why are you looking at me? I didn't do anything!";
	emotion ET_FRET,getnpcid(0,"King#illuvamp5");
	next;
	mes "[Antoine]",
		"Now that we know you exist, we can't ignore you. I can, but these people here can't. Their church won't allow it.";
	npctalk "So what's your point?","King#illuvamp5",bc_self;
	next;
	mes "[Antoine]",
		"We're not going to make any decision. Instead, we'll stay here with you.";
	next;
	mes "[King]",
		"So you can keep an eye on us. Drac, I can't take this anymore!";
	npctalk "I'm going to kill them all!","King#illuvamp5",bc_self;
	specialeffect 389,AREA,"King#illuvamp5";
	sleep2 250;
	specialeffect 583,AREA,"King#illuvamp5";
	sleep2 250;
	npctalk "Okay.","Wizard#illuvamp5",bc_self;
	next;
	mes "[King]",
		"What? Drac! Stop acting like a human! We're proud, dignified vampires!";
	emotion ET_FRET,getnpcid(0,"King#illuvamp5");
	next;
	mes "[Dracula]",
		"Let's go back. I'm tired. I want to sleep.";
	npctalk "Let me go with you. I want to stay with you until you fully recover.","Jojo#illuvamp5",bc_self;
	next;
	mes "[King]",
		"I'm not happy with this",
		"arrangment, Drac. I'm going back to our castle once you get better, got it?";
	emotion ET_ANGER,getnpcid(0,"King#illuvamp5");
	specialeffect 389,AREA,"King#illuvamp5";
	specialeffect 583,AREA,"King#illuvamp5";
	next;
	mes "[Gem]",
		"So we've come to an agreement.",
		"We'll leave now.";
	sleep2 2000;
	specialeffect 304,AREA,"Gem#illuvamp5";
	classchange HIDDEN_WARP_NPC,"Gem#illuvamp5",bc_self;
	next;
	mes "[Marina]",
		"You! I'm watching you! Better keep your coffin lid shut tight while you sleep!";
	sleep2 2000;
	specialeffect 304,AREA,"Marina#illuvamp5";
	classchange HIDDEN_WARP_NPC,"Marina#illuvamp5",bc_self;
	next;
	mes "[Antoine]",
		"I should leave too. Execuse me.";
	npctalk "What? Hey, you stop right there!","King#illuvamp5",bc_self;
	sleep2 2000;
	specialeffect 304,AREA,"Antoine#illuvamp5";
	classchange HIDDEN_WARP_NPC,"Antoine#illuvamp5",bc_self;
	next;
	specialeffect 583,AREA,"King#illuvamp5";
	mes "[King]",
		"Argh! I don't ever want to see them again! Let's go!";
	sleep2 2000;
	classchange HIDDEN_WARP_NPC,"King#illuvamp5",bc_self;
	next;
	mes "[Jojo]",
		"Let's go.";
	next;
	mes "[Dracula]",
		"Bomi, I'll see you when I get better.";
	next;
	mes "[Jojo]",
		"Okay, go.";
	specialeffect 583,AREA,"King#illuvamp5";
	specialeffect 304,AREA,"Jojo#illuvamp5";
	sleep2 1500;
	classchange HIDDEN_WARP_NPC,"Dracula#illuvamp5",bc_self;
	classchange HIDDEN_WARP_NPC,"Jojo#illuvamp5",bc_self;
	next;
	select("Finally, they all left. That was close.");
	mes "[Bomi]",
		"Thank you, Adventurer. Everything went well, and no one got hurt because of you.";
	next;
	select("You asked me if you looked like a human. Remember?");
	mes "[Bomi]",
		"I do.";
	next;
	select("What do you think defines a human?");
	mes "["+strcharinfo(0)+"]",
		"I didn't know you when you were a human, but I don't think you were different from who you are now. You're still trying to protect what's important to you.";
	next;
	mes "["+strcharinfo(0)+"]",
		"I think you're more human than anyone else I know. You also taught a vampire humanity.";
	next;
	mes "[Bomi]",
		"...Thank you. I never imagined someone would say such kind words to me one day, but I've longed to hear them.";
	next;
	mes "[Bomi]",
		"I couldn't get over the fact that I became a monster, but now I know better. I may not be a human anymore, but I'm still me.";
	next;
	mes "[Bomi]",
		"Thank you.";
	next;
	mes "["+strcharinfo(0)+"]",
		"I should go. It's time to report back.";
	next;
	mes "[Bomi]",
		"Okay. Travel safely. And thank you for your help.";
	//give quest
	completequest 14664;
	setquest 14665;
	illusion_vampire = 12;
	setpcblock PCBLOCK_ALL, 0;
	close;
}

if(illusion_vampire == 12){
	mes "[Bomi]",
		"Thank you.";
	next;
	mes "[Bomi]",
		"Please, travel safely. And thank you for your help.";
	close;
}

if(illusion_vampire == 14){
		.@q = checkquest(14671,HUNTING);
		disable_items;
		if(.@q > -1){
			if(10 > countitem(25269) || 10 > countitem(25268)){
				mes "[Bomi]",
					"Adventurer, did you forget what I asked? I need ^0000FF10 Sticky bloods from Matte Drainliars and 10 Mushroom Saps from Illusion Black Mushrooms^000000.",
					"Thank you.";
				close;
			}
			if(.@q != 2){
				mes "[Bomi]",
					"Adventurer, did you forget what I asked? Can you please hunt at least 5 Matte Drainliars and 5 Illusion Black Mushrooms",
					"Thank you.";
				close;
			}
			
			if(!checkweight(25271,1)){
				mes "- Please clear some weight before handing the quest -";
				close;
			}
			setpcblock PCBLOCK_ALL, 1;
			mes "[Bomi]",
				"Adventurer, thank you for bringing these to me.";
			next;
			mes "[Bomi]",
				"If I drink this toxic blood about thirty times, I might turn? Oh, never mind.";
			next;
			mes "[Bomi]",
				"Then please come back ^0000FFafer dawn^000000.";
			delitem 25269,10;
			delitem 25268,10;
			erasequest 14671;
			setquest 14674;
			getitem 25271,1;
			getexp 500000,500000;
			setpcblock PCBLOCK_ALL, 0;
			$bomi_quest_temp++;
			if($bomi_quest_temp >= 30){
				$bomi_quest_temp = 0;
				$illuvamp_bomiSpawned = true;
				close2;
				setpcblock PCBLOCK_ALL, 0;
				npctalk "O-oh, my..";
				mapannounce "gef_d01_i","O-oh, my..",bc_map;
				sleep2 1000;
				npctalk "H-have I drank.. too much?";
				mapannounce "gef_d01_i","H-have I drank.. too much?",bc_map;
				sleep2 1000;
				npctalk "Please.. S-stay away from me!";
				mapannounce "gef_d01_i","Please.. S-stay away from me!",bc_map;
				sleep2 5100;
				classchange HIDDEN_WARP_NPC,"Wizard#illuvamp",bc_self;
				monster "gef_d01_i",81,135,"Bomi",3756,1,strnpcinfo(0)+"::OnSummonDrac";
				end;
			}
			dispbottom (30 - $bomi_quest_temp) + " Quests left until Bomi turns.";
			close;
		}
		
		switch(checkquest(14674,PLAYTIME)){
			case -1:
			break;
			case 0:
			case 1:
			mes "[Bomi]",
				"Adventurer, thank you for trying to help me, but I don't want you to strain yourself. Why don't you rest for now?";
			next;
			mes "[Bomi]",
				"You can come back ^0000FFafer dawn^000000.";
			close;
			case 2:
			mes "[Bomi]",
				"Adventurer, weclome back. Could you help me today as usual?";
			next;
			mes "[Bomi]",
				"I need ^0000FF10 Sticky bloods from Matte Drainliars and 10 Mushroom Saps from Illusion Black Mushrooms^000000.",
				"You can get them if you hunt at least 5 Matte Drainliars amd 5 Illusion Black Mushrooms.";
			next;
			mes "[Bomi]",
				"Thank you for your help.";
			
			setquest 14671;
			erasequest 14674;
			close;
			break;
		}
		
		
	mes "[Bomi]",
		"Adventurer, did you report already? Do you have something else to do here?";
	next;
	mes "[Bomi]",
		"If you're not busy, could you help",
		"me with something?";
	next;
	if(select("Sure thing.", "I'm kind of busy at the moment.") == 2){
		mes "[Bomi]",
			"Oh, are you? I'm sorry. Maybe you could come back later? No, never mind.";
		close;
	}
	
	mes "[Bomi]",
		"As you kmow, I live on that fake blood that I make with the ingredients I find around here. I'm thinking I'll make some more for Dracula as well.";
	next;
	mes "[Bomi]",
		"But since this fake blood is not pure, drinking it regularly causes your body to accumulate toxins, which drive you insane until they are completely purged from your system.";
	next;
	mes "[Bomi]",
		"But maybe that only happens to me. I'm a new vampire, and I'm weak. Dracula has lived for a long time, and he's anything but weak.";
	next;
	mes "[Bomi]",
		"Anyway, I need ^0000FF10 Sticky bloods from Matte Drainliars and 10 Mushroom Saps from Illusion Black Mushrooms^000000.";
	next;
	mes "[Bomi]",
		"You can find them if you want at least 5 Matte Drainliars and 5 Illusion Black Mushrooms.";
	setquest 14671;
	close;
}

end;

OnSummonDrac:
	$illuvamp_bomiSpawned = false;
	$illuvamp_dracSpawned = true;
	mapannounce "gef_d01_i","Bomi... Bomi is dead?!",bc_map;
	sleep2 1000;
	mapannounce "gef_d01_i","I always knew that these humans are Untrustworthy!",bc_map;
	getmapxy(.@map$,.@x,.@y,BL_PC);
	monster .@map$,.@x,.@y,"Enraged Dracula",3757,1,strnpcinfo(0)+"::OnDracDeath";
end;

OnDracDeath:
	$illuvamp_dracSpawned = false;
	mapannounce "gef_d01_i","B-Bomi... I'm coming to.. rest with you..",bc_map;
end;

OnTouch:
	if(illusion_vampire == 6){
		setpcblock PCBLOCK_ALL, 1;
		npctalk "This one has a different color from Illusion black mushrooms. Is it a new kind? I'd better pick it carefully...", "Wizard#illuvamp", bc_self;
		sleep2 2250;
		unittalk getcharid(3), strcharinfo(0) + " : Typical wizard... Wait, could that be Jojo?",bc_self;
		sleep2 2250;
		setpcblock PCBLOCK_ALL, 0;
	}
end;

OnInit:
	$illuvamp_bomiSpawned = false;
	questinfo 14664,QTYPE_QUEST,1;
	setquestinfo_req 14664,14663,1;
	questinfo 14665,QTYPE_QUEST,1;
	setquestinfo_req 14665,14664,1;
	
	questinfo 14671,QTYPE_QUEST,1;
	setquestinfo_req 14671,14666,2,14674,0;
end;

OnPCLoadMapEvent:
if(strcharinfo(3)=="gef_d01_i" && checkquest(14674,PLAYTIME)==2)
	showevent QTYPE_QUEST,1;
end;
}

// =========================
//	End Found Bomi
// =========================


// =========================
//	Found Jojo
// =========================

gef_d01_i,189,98,2	script	Dracula#illuvampinv	HIDDEN_WARP_NPC,11,11,{
end;
OnTouch:
	if(illusion_vampire >= 9 && illusion_vampire != 11){
		classchange 4_NFBAT,"King#illuvamp",bc_self;
		classchange 735,"Wizard#illuvamp3",bc_self;
		if(illusion_vampire == 14 && $illuvamp_dracSpawned)
			end;
			
		classchange 4_DRACULA,"Dracula#illuvamp2",bc_self;
	}
end;
OnInit:
	$illuvamp_dracSpawned = false;
end;
}

gef_d01_i,185,96,5	script	King#illuvamp	HIDDEN_WARP_NPC,{
if(illusion_vampire == 9){
	mes "[King]",
		"What, do you have business with me? If not, shoo!";
	close;
}

if(illusion_vampire == 10 || illusion_vampire == 11){
	mes "[King]",
		"I smell blood! Human blood!";
	next;
	mes "[Jojo]",
		"You can't be smelling me. I'm not bleeding anymore. I already healed!";
	next;
	mes "[King]",
		"No. It's from somewhere else, and I'm smelling more than one human.",
		"...^0000FFA fight!^000000 A fight broke out somewhere! Blood! Let's go!";
	next;
	mes "["+strcharinfo(0)+"]",
		"A fight? ...No. What if the people from the Church found Bomi?";
	next;
	mes "[Dracula]",
		"What people from the Church?";
	next;
	mes "[King]",
		"*Sniff* This way! The smell is coming from this way!";
	emotion ET_GO,getnpcid(0,"King#illuvamp");
	//give quest
	if(!isbegin_quest(14663)){
		completequest 14662;
		setquest 14663;
	}
	close2;
	// mark location (Bomi)
	viewpoint 1,81,135,1,0xFF0000;//shoud be pink/purple
	end;
}

if(illusion_vampire == 12){
	mes "[King]",
		"Why are you looking at me like that? Dracula needs more rest. Do not disturb him.";
	close;
}

if(illusion_vampire == 14){
		.@q = checkquest(14675,HUNTING);
		disable_items;
		if(.@q > -1){
			mes "[King]",
				"You came back quickly. I hope you didn't forget anything.";
			next;
			if(20 > countitem(25263)){
				mes "[King]",
					"Look what we've got here. Did you",
					"forget what I asked? I told you to",
					"hunt 10 Matte Drainliars and bring",
					"20 Short Bat Hairs.";
				next;
				mes "[King]",
					"Go get it done.";
				close;
			}
			if(.@q != 2){
				mes "[King]",
					"Look what we've got here. Did you",
					"forget what I asked? These 10 Matte",
					"Drainliars are still flapping around",
					"here.";
				next;
				mes "[King]",
					"Go get it done.";
				close;
			}
			
			if(!checkweight(25271,1)){
				mes "- Please clear some weight before handing the quest -";
				close;
			}
			setpcblock PCBLOCK_ALL, 1;
			mes "[King]",
				"Wizard! The adventurer has brought",
				"the hair.";
			next;
			mes "[Jojo]",
				"What am I supposed to do now?";
			next;
			mes "[King]",
				"That's for you to figure out. I'm",
				"not a cape maker, am I? But I know",
				"you would need more than that.";
			next;
			mes "[Jojo]",
				"Um... Adventurer?";
			next;
			mes "[King]",
				"He just came back from hunting. You should let him rest, at least for the rest of the day.";
			next;
			mes "[King]",
				"Adventurer, come back tomorrow and",
				"hunt more Matte Drainliars for me,",
				"will you? It's so quiet without them.";
			next;
			mes "[King]",
				"The-then see you tomoorow, Adventurer...";
			delitem 25263,20;
			erasequest 14675;
			setquest 14676;
			getitem 25271,1;
			getexp 500000,500000;
			setpcblock PCBLOCK_ALL, 0;
			close;
		}
		
		switch(checkquest(14676,PLAYTIME)){
			case -1:
			break;
			case 0:
			case 1:
			mes "[Jojo]",
				"Adventurer, you're back already.";
			next;
			mes "[King]",
				"Yes, why did you come back so",
				"quickly? I don't want to be",
				"disturbed right now. Come back later.";
			close;
			case 2: //TODO
			mes "[King]",
				"The adventurer is here!";
			next;
			mes "[Jojo]",
				"The adventurer is here!";
			next;
			select("Why are you so excited to see me?");
			mes "[King]",
				"You'll take care of those Matte Drainliars like you did the last time, right? They're too loud.";
			next;
			mes "[Jojo]",
				"And you'll get some short bat hair too, right? I need a lot more than what you brought last time.";
			next;
			mes "[King]",
				"10 Matte Drainliars!";
			next;
			mes "[Jojo]",
				"Thank you in advance!";
			setquest 14675;
			erasequest 14676;
			close;
			break;
		}
	
	mes "[Jojo]",
		"Ah, Adventurer. Good to see you",
		"again! Dracula is doing better,",
		"though he sleeps all day.";
	next;
	mes "[King]",
		"He's fully recovered, be he still",
		"doesn't want to leave. I don't know why he's so infatuated with that turned human.";
	next;
	mes "[Jojo]",
		"Oh, do you mean Bomi? I thought she was a vampire like Dracula.";
	next;
	mes "[King]",
		"Not all vampires are the same.",
		"We're different from her. By the",
		"way, why are you still here?",
		"Dracula doesn't need you anymore.";
	next;
	mes "[Jojo]",
		"Well, there are things around here",
		"that I want to study, and...";
	next;
	mes "[King]",
		"Do you have a death wish? Haven't",
		"you noticed how hungry and",
		"ferocious these bats are? They",
		"latch into anything that moves,",
		"these creeps! Take care of them for me, will you?";
	next;
	if(select("They're annoying.", "Um, I'm kind of busy.") == 2){
		mes "[King]",
			"Oh, are you? Then go. Go away.";
		next;
		mes "[Jojo]",
			"King, you have to be so mean.";
		next;
		mes "[King]",
			"He was mean to me first! And he",
			"said he's busy. That's why I said",
			"go. Go!";
		close;
	}
	
	mes "[Jojo]",
		"Well, they don't bother me as long",
		"as I stay close to Dracula and King.";
	next;
	mes "[King]",
		"But they drink zombie blood! Yuck!",
		"I'll never drink dead blood, no",
		"matter how hungry I am. That's",
		"disgraceful!";
	next;
	mes "[Jojo]",
		"So you're hating your own kind.";
	npctalk "What? You, human.","King#illuvamp",bc_self;
	sleep2 2000;
	npctalk "Yes...?","Wizard#illuvamp3",bc_self;
	sleep2 1000;
	npctalk "Am I a bat?","King#illuvamp",bc_self;
	sleep2 1000;
	npctalk "...No.","Wizard#illuvamp3",bc_self;
	next;
	mes "[King]",
		"In case you have forgotten, do you",
		"know how you're still standing",
		"there, breathing?";
	next;
	mes "[Jojo]",
		"...How?";
	next;
	mes "[King]",
		"Because I let you. And I'm letting",
		"you breathe not because you're",
		"worth living, but because I'm too",
		"lazy to kill you.";
	next;
	mes "[Jojo]",
		"...Oh. Thank you for everything.",
		"Um, I think it's time I should",
		"rejoin my group.";
	emotion ET_SWEAT,getnpcid(0, "Wizard#illuvamp3");
	next;
	mes "[King]",
		"I'm still talking to you. You're",
		"not afraid of me because I'm in bat form, are you? You humans are so stupid, you can't get past what you see.";
	npctalk "No, no, that's not true.","Wizard#illuvamp3",bc_self;
	next;
	mes "[Jojo]",
		"I agree that these bats are",
		"disgraceful, shameless, and ",
		"disgusting animals.";
	next;
	mes "[King]",
		"Did you just call me a disgusting animal?";
	next;
	mes "[Jojo]",
		"No, no. Not you. I'm talking about Matte Drainliars.";
	npctalk "Good, because you don't want to make me angry.","King#illuvamp",bc_self;
	sleep2 2000;
	npctalk "It seems you already identify yourself as a bat.","Wizard#illuvamp3",bc_self;
	sleep2 2000;
	npctalk "What?","King#illuvamp",bc_self;
	next;
	select("I have question for you, King.");
	mes "[King]",
		"What is it?";
	next;
	select("Why are you in bat form?");
	mes "[Jojo]",
		"Yes. If you hate them so much, then why don't you go back to your original form?";
	next;
	mes "[King]",
		"That's because this form is more efficient. I don't have to drink a lot to get full, I'm inconspicuous, and people? Like that numskull over there? Let their guard down around me.";
	next;
	mes "[Jojo]",
		"I'm not a numskull. I wouldn't have become a wizard if I was. And don't forget, I saved Dracula!";
	next;
	mes "["+strcharinfo(0)+"]",
		"But why a bat? There are other",
		"small animals.";
	next;
	mes "[King]",
		"Because bats are stealthy, and they can fly. Oh, speaking of which, did you know the short hair of Matte Drainliars is used for making cloaking capes?";
	next;
	select("Huh? No, I've never heared that.");
	mes "[Jojo]",
		"Cloaking capes? Thieves and their",
		"ilk must love those.";
	next;
	mes "[King]",
		"I can't believe how simple-minded",
		"you are.";
	next;
	mes "[Jojo]",
		"Erm, how can I get the hair? By",
		"hunting Matte Drainliars?";
	next;
	mes "[King]",
		"Why, do you want to quit magic and",
		"turn to thievery?";
	next;
	mes "[Jojo]",
		"No. But it's always been my dream",
		"to conquer all the dungeons on the",
		"continent and become the greatest mage.";
	next;
	mes "[King]",
		"...That's a big dream, an",
		"impossible dream. Well, anyone can",
		"dream big.";
	npctalk "Argh, come one!","Wizard#illuvamp3",bc_self;
	sleep2 1500;
	npctalk "Come on, What?","King#illuvamp",bc_self;
	next;
	mes "[Jojo]",
		"Even if it's not for my dream, a",
		"cloaking cape will come in handy in various situations.";
	next;
	mes "[King]",
		"I didn't know there was an aspiring theif among us. Huh.";
	next;
	mes "[Jojo]",
		"I said not what I want.",
		"Adventurer, are you busy?";
	next;
	mes "[King]",
		"What, you're going to ask him? Do",
		"it yourself!";
	next;
	mes "[Jojo]",
		"I have other things to do.";
	next;
	mes "[King]",
		"Like what? Eating, sleeping, and pooping?";
	next;
	mes "[Jojo]",
		"Oh, oome on! You know I've been",
		"busy studying things!";
	next;
	mes "[King]",
		"You mean, studying me and Dracula.";
	next;
	mes "[Jojo]",
		"...How did you... ?";
	next;
	mes "[King]",
		"I've known that from the beginning. Your face is so transparent, you can't hide anything. I just didn't say anything because I found it funny that you nervously kept glancing at us.";
	next;
	mes "[Jojo]",
		"...Oh, Then can I ask you",
		"questions?";
	npctalk "No.","King#illuvamp",bc_self;
	sleep2 1000;
	npctalk "Why not?!","Wizard#illuvamp3",bc_self;
	sleep2 1000;
	next;
	mes "[King]",
		"Adventurer, are you going to get the bat hair for him? Good, that means you'll take care of those Matte Drainliars. Their flapping their wings keep me awake at night.";
	next;
	mes "[Jojo]",
		"Why can't you do it yourself? All you have to do is just flick your finger.";
	next;
	mes "[King]",
		"I can flick my finger at you if you want.";
	next;
	mes "[Jojo]",
		"Adventurer, please bring me the bat hair. King? I mean, Mr. King? How much bat hair do I need?";
	next;
	mes "[King]",
		"That depends on what kind of cape",
		"you want. Just know that it's tough to make stuff with hair.";
	next;
	mes "[Jojo]",
		"Um, okay, then please bring me 20",
		"Short Bat Haris for starters.";
	next;
	mes "[King]",
		"While you're at it, hunt the Matte",
		"Drainliars around us. They are at",
		"least 10.";
	next;
	mes "[Jojo]",
		"Happy hunting, Adventurer!";
	
	setquest 14675;
	close;
}

end;
OnInit:
	questinfo 14663,QTYPE_QUEST,1;
	setquestinfo_req 14663,14662,1;
	
	questinfo 14675,QTYPE_QUEST,1;
	setquestinfo_req 14675,14666,2,14676,0;
end;

OnPCLoadMapEvent:
if(strcharinfo(3)=="gef_d01_i" && checkquest(14676,PLAYTIME)==2)
	showevent QTYPE_QUEST,1;
end;
}

gef_d01_i,191,96,4	script	Wizard#illuvamp3	HIDDEN_WARP_NPC,{
if(illusion_vampire == 9){
	mes "[Jojo]",
		"How's Mojo doing? Heh, she's so curious, I feel sorry for Brother Grimm for having to deal with her.";
	next;
	mes "[Jojo]",
		"I can't leave here just yet. There are still many things in this place I want to know about.";
	close;
}

if(illusion_vampire == 10 || illusion_vampire == 11){
	if(!isbegin_quest(14663)){
		mes "[Jojo]",
			"What's he smelling?";
		next;
		mes "[Jojo]",
			"I'm not bleeding right?! Am I still bleeding?!?!";
		close;
	}
	mes "[Jojo]",
		"A fight has broke out somewhere over there. Don't you want to go check?";
	close;
}

if(illusion_vampire == 12 || illusion_vampire == 13){
	mes "[Jojo]",
		"I'm going to stay here for a while. I'll take a while before Dracula fully regains his energy, and personally, there are many things that I want to know about these people.";
	next;
	mes "[Jojo]",
		"Please let Nun Gem and Mojo know.";
	close;
}

if(illusion_vampire == 14){
		.@q = checkquest(14677,HUNTING);
		disable_items;
		if(.@q > -1){
			mes "[Jojo]",
				"Adventurer, weclome back!";
			next;
			if(10 > countitem(25264) || 10 > countitem(25265)){
				mes "[King]",
					"I can tell that's not enough, just",
					"by looking at it.";
				next;
				mes "[Jojo]",
					"Oh, you're right. You must have",
					"forgotten what I asked.";
				next;
				mes "[Jojo]",
					"Please bring me",
					"10 Shining Spores from Illusion",
					"Black Mushrooms and 10 Clusters of",
					"Nightmares from Sweet Nightmares. Thank you.";
				close;
			}
			if(.@q != 2){
				mes "[Jojo]",
					"Adventurer... From where did you get these?",
					"Please go hunt 5 Illusion Black Mushrooms and 5 Sweet Nightmares.";
				close;
			}
			
			if(!checkweight(25271,1)){
				mes "- Please clear some weight before handing the quest -";
				close;
			}
			setpcblock PCBLOCK_ALL, 1;
			mes "[King]",
				"I can tell he brought everything",
				"you asked. Come on, make a paste",
				"and apply it to the wall already.";
			next;
			mes "[Jojo]",
				"Adventurer, thank you for helping",
				"me study. These glowing spores",
				"don't last long. Could you come",
				"back tomorrow and get more of them?";
			delitem 25264,10;
			delitem 25265,10;
			erasequest 14677;
			setquest 14678;
			getitem 25271,1;
			getexp 500000,500000;
			setpcblock PCBLOCK_ALL, 0;
			close;
		}
				
		switch(checkquest(14678,PLAYTIME)){
			case -1:
			break;
			case 0:
			case 1:
			mes "[Jojo]",
				"Adventurer, see this luminous glow over there? It's from the shining spores you brought to me.";
			next;
			mes "[Jojo]",
				"I feel as if I traveled back in time, studying by this dim light.";
			next;
			mes "[Jojo]",
				"I still have enough light left in these shining spores. Please come back ^0000FFafer dawn^000000.";
			close;
			case 2: //TODO
			mes "[Jojo]",
				"Adventurer! You're the light of my life!";
			next;
			mes "[King]",
				"You're scaring him.";
			next;
			mes "[Jojo]",
				"Could you get me shining spores again today?";
			next;
			mes "[Jojo]",
				"Please bring me 10 Shining Spores from Illusion Black Mushrooms and 10 Clusters of Nightmares from Sweet Nightmares. Thank you.";
			setquest 14677;
			erasequest 14678;
			close;
			break;
		}
		
	mes "[Jojo]",
		"Adventurer, wait!";
	next;
	mes "[King]",
		"You misspelled that.";
	next;
	mes "[Jojo]",
		"Where? Oh, I did it again.";
	next;
	mes "[King]",
		"Tsk, tsk. I don't know how you've",
		"become a wizard when you can't even spell correctly.";
	next;
	mes "[Jojo]",
		"This is only because it's too dark",
		"to see. And stop peeking at what",
		"I'm doing.";
	next;
	mes "[King]",
		"It's not like you're writing",
		"something important.";
	next;
	select("You two get along aw well as I remember.");
	mes "[King]",
		"What are you doing here? Don't you",
		"have things to do?";
	next;
	if(select("Jojo wanted to see me.", "Actually I'm busy.") == 2){
		mes "[Jojo]",
			"Are you? I was going to ask you a favor, but I can wait.";
		next;
		mes "[King]",
			"Then you'd better go attend your business.";
		close;
	}
	
	mes "[King]",
		"Why?";
	next;
	mes "[Jojo]",
		"Since we're underground, it's too",
		"dark for me to write and read. I",
		"have a lot of information that I",
		"want to catalog, but I keep",
		"misspelling words because I can't",
		"see them clearly.";
	next;
	mes "[King]",
		"You should be able to do that with",
		"your eyes closed. You're a wizard.",
		"Didn't you learn how to summon light? But of course, if you use magic in front of me, I'll burn you to ashes.";
	npctalk "I... I'm still a wizard!","Wizard#illuvamp3",bc_self;
	sleep2 1500;
	npctalk "What? I can't hear you.","King#illuvamp",bc_self;
	next;
	mes "[Jojo]",
		"I completed my guild's official wizard training program. I'm strong enough to have a contest with you!";
	next;
	mes "[King]",
		"Oh, really? Good for you!";
	next;
	mes "[King]",
		"Be honet, though. Did you really study hard? Did you attend every class, study all night, and practice hard? You'd better tell me the truth.";
	next;
	mes "[King]",
		"Can you honestly say that you tried to push past your limits?";
	next;
	mes "[Jojo]",
		"...";
	next;
	mes "[King]",
		"No, you didn't. That's why you had",
		"your butt handed to you by those",
		"mushrooms.";
	next;
	mes "[Jojo]",
		"I said they were zombies, not mushrooms!";
	next;
	mes "[King]",
		"Zombies and mushrooms. Same difference to me.";
	next;
	mes "[King]",
		"You're not good enough to earn your keep. I can't believe your guild actually invested in you.";
	npctalk "I've been earning my keep just fine.","Wizard#illuvamp3",bc_self;
	sleep2 1500;
	npctalk "Yeah, right.","King#illuvamp",bc_self;
	next;
	mes "[Jojo]",
		"Then what about you? I know you can transform. But what else can you do?";
	npctalk "Do you really want me to show you? Right now?","King#illuvamp",bc_self;
	sleep2 2000;
	npctalk "...No.","Wizard#illuvamp3",bc_self;
	next;
	mes "[King]",
		"Maybe you keep questioning me",
		"because you can't trust me. How",
		"about I teach you to be the",
		"greatest mage among humans? would",
		"you trust me, then?";
	next;
	mes "[Jojo]",
		"Erm, you want to teach me?";
	next;
	mes "[King]",
		"Sure.";
	next;
	mes "[Jojo]",
		"Why?";
	next;
	mes "[King]",
		"I've studied a lot. Why do you think I have?";
	next;
	mes "[Jojo]",
		"To become smarter?";
	next;
	mes "[King]",
		"No. Because I was bored to death!";
	next;
	mes "[Jojo]",
		"You have all the time in the world. I'm envious of that.";
	next;
	mes "[King]",
		"If you don't want me to teach you, that's fine by me.";
	next;
	mes "[Jojo]",
		"No, no! I'd love to! But... erm...",
		"you're not going to ask my blood in return, are you?";
	next;
	mes "[King]",
		"If I drank anything because I'm thirsty, I wouldn't be any better than those Matter Drainliars now, would I?";
	npctalk "Did you just compare me to zombies?","Wizard#illuvamp3",bc_self;
	sleep2 2000;
	npctalk "So you're not as stupid as I thought.","King#illuvamp",bc_self;
	next;
	select("Jojo?");
	mes "[Jojo]",
		"Oh, I'm sorry, I didn't mean to",
		"keep you standing there. Could you",
		"get me some spores from Illusion",
		"black mushrooms? I need some light",
		"to see what I'm writing.";
	npctalk "Why those?","King#illuvamp",bc_self;
	next;
	mes "[Jojo]",
		"Oh, you know how those spores glow? I want to use them to illuminate this place.";
	next;
	mes "[King]",
		"Well, then go get them yourself.",
		"Don't dump things on this adventurer.";
	next;
	mes "[Jojo]",
		"Oh, well... I'm... Illusion Black",
		"Mushrooms are... You know.";
	npctalk "You said you were attacked by zombies.","King#illuvamp",bc_self;
	sleep2 2000;
	npctalk "I was.","Wizard#illuvamp3",bc_self;
	next;
	mes "[King]",
		"Where are you going to put the",
		"spores, anyway?";
	next;
	mes "[Jojo]",
		"I have an empty bottle- oh,I",
		"forgot I lost my bag when I was",
		"attacked.";
	next;
	mes "[Jojo]",
		"Adventurer, could you get me some",
		"Cluster of Nightmares as well? I",
		"can mix them with the spores to",
		"make a paste and apply it on the wall.";
	next;
	mes "[King]",
		"What? That's so tacky.";
	next;
	mes "[Jojo]",
		"But effective nonetheless. You didn't know you could use them like that, did you?";
	next;
	mes "[King]",
		"Because I didn't need to.";
	next;
	mes "[Jojo]",
		"Then, Adventurer, please bring me",
		"10 Shining Spores from Illusion",
		"Black Mushrooms and 10 Clusters of",
		"Nightmares from Sweet Nightmares.";
	
	setquest 14677;
	close;
}

end;

OnInit:
	questinfo 14677,QTYPE_QUEST,1;
	setquestinfo_req 14677,14666,2,14678,0;
end;
OnPCLoadMapEvent:
if(strcharinfo(3)=="gef_d01_i" && checkquest(14678,PLAYTIME)==2)
	showevent QTYPE_QUEST,1;
end;
}

gef_d01_i,189,98,3	script	Dracula#illuvamp2	HIDDEN_WARP_NPC,{
if(illusion_vampire == 9){
	setpcblock PCBLOCK_ALL, 1;
	npctalk "Let's drink from this one.","King#illuvamp",bc_self;
	sleep2 3000;
	npctalk "Oh, no. That's...","Wizard#illuvamp3",bc_self;
	emotion ET_SWEAT,getnpcid(0,"Wizard#illuvamp3");
	sleep2 3000;
	npctalk "King, I told you, we are not drinking from people anymore. And that's not a polite thing to say. I apologize on his behalf.","Dracula#illuvamp2",bc_self;
	sleep2 5000;
	npctalk "I-it's okay.","Wizard#illuvamp3",bc_self;
	sleep2 3000;
	npctalk "Humans die eventually. Is it so bad to die a little bit earlier? Come on, let's have a drink. This one doesn't smell good, though.","King#illuvamp",bc_self;
	sleep2 5000;
	npctalk "Do you mind if I get rid of that bat?","Wizard#illuvamp3",bc_self;
	sleep2 3000;
	npctalk "No one hurts anyone infront of me.","Dracula#illuvamp2",bc_self;
	sleep2 3000;
	npctalk "Human, are you blind? I'm not a bat.","King#illuvamp",bc_self;
	emotion ET_FRET,getnpcid(0,"King#illuvamp");
	sleep2 3000;
	npctalk "Then what are you?","Wizard#illuvamp3",bc_self;
	sleep2 3000;
	specialeffect 389,AREA,"King#illuvamp";
	sleep2 500;
	specialeffect 583,AREA,"King#illuvamp";
	npctalk "Now, what what do I look like?","King#illuvamp",bc_self;
	sleep2 3000;
	npctalk "*Gasp* What the hell are you?","Wizard#illuvamp3",bc_self;
	//omg wiz
	emotion ET_HUK,getnpcid(0,"Wizard#illuvamp3");
	sleep2 3000;
	npctalk "Why, is this too scary? Then how about this?","King#illuvamp",bc_self;
	sleep2 3000;
	specialeffect 389,AREA,"King#illuvamp";
	sleep2 500;
	specialeffect 583,AREA,"King#illuvamp";
	sleep2 250;
	classchange 735,"King#illuvamp",bc_self;
	npctalk "Y-y-you're me? D-d-d-doppelganger! A-am I going to die?!","Wizard#illuvamp3",bc_self;
	emotion ET_CRY,getnpcid(0,"Wizard#illuvamp3");
	sleep2 3000;
	npctalk "You're afraid of yourself. Why?","King#illuvamp",bc_self;
	sleep2 3000;
	npctalk "You love yourself so much that you don't accept anyone that doesn't look like you. But when you see someone that looks exactly like you, you can't tolerate it. Why?","King#illuvamp",bc_self;
	sleep2 5000;
	npctalk "Seeing other humans and seeing a clone of myself are two different things!","King#illuvamp",bc_self;
	sleep2 5000;
	npctalk "King, that's enough. Stop torturing him.","Dracula#illuvamp2",bc_self;
	sleep2 3000;
	emotion ET_OHNO,getnpcid(0,"King#illuvamp");
	specialeffect 389,AREA,"King#illuvamp";
	sleep2 500;
	specialeffect 583,AREA,"King#illuvamp";
	sleep2 250;
	classchange 4_NFBAT,"King#illuvamp",bc_self;
	npctalk "Tsk, tsk. You're too softhearted when it comes to humans.","King#illuvamp",bc_self;
	sleep2 5000;
	npctalk "Um... I can move fine now. Can I go?","Wizard#illuvamp3",bc_self;
	sleep2 3000;
	npctalk "Yes, you can leave.","Dracula#illuvamp2",bc_self;
	sleep2 3000;
	npctalk "No!","King#illuvamp",bc_self;
	sleep2 3000;
	npctalk "Why not?","Dracula#illuvamp2",bc_self;
	sleep2 3000;
	npctalk "He's a human, and humans move in groups. He's going to bring his friends to attack us. Did you forget that already?","King#illuvamp",bc_self;
	sleep2 5000;
	npctalk "No, I'm not going to do that. I never forget favors. You've saved me. I promise I won't hurt you. Please believe me.","Wizard#illuvamp3",bc_self;
	sleep2 5000;
	npctalk "Humans can't be trusted, ever.","King#illuvamp",bc_self;
	sleep2 3000;
	npctalk "I agree that he might bring his friends, but not all humans are untrustworthy..","Dracula#illuvamp2",bc_self;
	sleep2 5000;
	npctalk "Whose side are you on? Me or him?","King#illuvamp",bc_self;
	sleep2 3000;
	unittalk getcharid(3), strcharinfo(0) + " : Typical wizard... Wait, could that be Jojo??",bc_self;
	mes "["+strcharinfo(0)+"]",
		"Typical wizard... Wait, could that be Jojo??";
	next;
	if(select("Jojo? Are you Jojo?") != 1)
		setpcblock PCBLOCK_ALL, 0;
	
	mes "[Jojo]",
		"Wh-who are you?";
	sleep2 500;
	npctalk "See, I told you! One of his friends already showed up! This is why I don't trust humans!","King#illuvamp",bc_self;
	sleep2 500;
	npctalk "A human?","Dracula#illuvamp2",bc_self;
	sleep2 500;
	next;
	mes "[Jojo]",
		"No, no! He's not my friend! I've never seen him before in my life, I swear!";
	next;
	mes "[King]",
		"He could be sent by your friends. Human, answer me!";
	next;
	select("Jojo's colleagues are looking for him.");
	npctalk "No! They're going to put us in danger!","King#illuvamp",bc_self;
	mes "[Stranger]",
		"I see. We found him injured and uncnscious, so we took him here and treated him. He's well enough to leave now.";
	next;
	select("You saved Jojo");
	mes "["+strcharinfo(0)+"]",
		"Let me thank you on behalf of his colleagues. May I ask your name?";
	next;
	mes "[King]",
		"You're here, and yet you don't know who he is. He's Dracula. Didn't you come to challenge him to battle?";
	next;
	mes "["+strcharinfo(0)+"]",
		"Dracula? You mean the Dracula?";
	next;
	mes "[Dracula]",
		"You have a familiar smell about you, Adventurer, I've yearned for this smell for a long time.";
	npctalk "Are you saying he smells delicious? Can I drink from him?","King#illuvamp",bc_self;
	next;
	mes "[Dracula]",
		"I mean he smells like a friend, Little One.";
	npctalk "What friend? I thought I was the only friend you had.","King#illuvamp",bc_self;
	next;
	select("I met Bomi before I came here.");
	mes "[Dracula]",
		"...I see. How is she?";
	sleep2 1000;
	npctalk "What? Bomi?","King#illuvamp",bc_self;
	sleep2 1000;
	npctalk "You mean the owner of the notebook?","Wizard#illuvamp3",bc_self;
	sleep2 1000;
	npctalk "Did she tell you anything about... me?","Dracula#illuvamp2",bc_self;
	next;
	mes "[King]",
		"Wow, so you've been hanging around here all this time because of that ungreatful girl. Is that it?";
	npctalk "She's not ungreatful. She never wanted what I gave her.","Dracula#illuvamp2",bc_self;
	next;
	mes "[Jojo]",
		"What did you give her?";
	next;
	mes "[King]",
		"Eternal life.";
	next;
	mes "[Jojo]",
		"Eternal life..!";
	next;
	mes "[King]",
		"That's the normal reaction from humans! She's ungreatful!";
	npctalk "Why, do you want it? I can give it to you.","King#illuvamp",bc_self;
	next;
	select("She said Dracula betrayed her.");
	mes "[King]",
		"Betrayed her? Hah? Where is she? He should've just let her die!";
	emotion ET_FRET,getnpcid(0,"King#illuvamp");
	next;
	mes "[Dracula]",
		"She still hasn't forgiven me. But I did what I had to do.";
	next;
	select("There must be some misunderstanding.");
	mes "[Dracula]",
		"I needed some humans to survive. I hid among them and hunted with them whenever I needed.";
	next;
	mes "[Dracula]",
		"One day, people from the Church found me. They were bent on killing me in the name of justice.";
	npctalk "They were presistent.","King#illuvamp",bc_self;
	next;
	mes "[Dracula]",
		"I was gravely injured by them, and somehow I ended in this place full of death and mysterious energy.";
	next;
	mes "[Dracula]",
		"I thought I was going to die here, but then Lady Luck finally turned her gaze upon me.";
	npctalk "Somebody please shut him up. I hate this story.","King#illuvamp",bc_self;
	next;
	mes "[Dracula]",
		"Bomi saved me. She fed me her blood, so I could regain my strength. I'm not a living being, but that day, she gave me new life.";
	next;
	mes "[Jojo]",
		"Why didn't you leave afterward?";
	next;
	mes "[Dracula]",
		"Even though Bomi was a strong woman, her body was failing her. It pained me to see her waste away day by day. I offered her eternal life, and she rejected it.";
	next;
	mes "[Dracula]",
		"I stayed because I wanted to be there for her when she died as a human.";
	next;
	mes "[Dracula]",
		"For the first time in my long existence, I really thought about humans, and what made them who they were. They also have this impulse to help others, expecting nothing in return.";
	next;
	mes "[Dracula]",
		"I'd learned about them through Bomi. What I'd learned didn't make sense, and I didn't really understand it.";
	next;
	mes "[Dracula]",
		"But it was different from the I previously thought of humans. I was starting to understand them.";
	npctalk "Why? What good would understanding them do you?","King#illuvamp",bc_self;
	next;
	mes "[Jojo]",
		"Then why did you turn her against her wish?";
	next;
	mes "[Dracula]",
		"There was an accident. The people who almost killed me found me again.";
	npctalk "The people from the Church?","Wizard#illuvamp3",bc_self;
	next;
	mes "[Dracula]",
		"Bad luck follows me wherever I go. Bomi even made me a lucky charm, but it didn't work.";
	next;
	mes "[Dracula]",
		"By then, I'd fully regained my strength, and those humans weren't a match for me. But Bomi... she didn't want anyone to get hurt.";
	next;
	mes "[Dracula]",
		"Long story short, she got caught in the crossfire. She was dying and I panicked.";
	next;
	mes "[Dracula]",
		"I wasn't ready to let her go. Before I had time to think about what I was doing, I turned her.";
	next;
	mes "[Jojo]",
		"You did it because you didn't want to lose her. I would've done the same in that situation.";
	npctalk "Why?","King#illuvamp",bc_self;
	sleep2 500;
	npctalk "That's what people do, to protect those they love.","Wizard#illuvamp3",bc_self;
	sleep2 500;
	next;
	mes "[King]",
		"But, that stubborn girl refuses to ackowldge that!";
	next;
	mes "[King]",
		"I don't understand her logic. How could she possibly want to die as a human than to live as a vampire? How could she think the gift of eternal life is betrayal?";
	next;
	mes "[Jojo]",
		"I think I know. People tend to take things for granted. If I could live forever, I think I'd lose all my motivation. I mean, you have nothing but time.";
	next;
	mes "[Jojo]",
		"I think you guys need to talk it out with each other. Have you tried to talk to her?";
	next;
	mes "[Dracula]",
		"When she was brought back to life, she was so shocked and angry that she wouldn't listen to me.";
	next;
	mes "[Dracula]",
		"I did what I did to save her, and I understand she resents me for it.";
	npctalk "You need to stop hanging with humans. You sound like one of them now.","King#illuvamp",bc_self;
	next;
	mes "[King]",
		"Dracula, what's that human to you? Why, do you insist on staying in a place like this?";
	npctalk "When she won't even talk to you?","King#illuvamp",bc_self;
	next;
	mes "[Dracula]",
		"I'm not?";
	next;
	mes "[King]",
		"Everyone, hush. I smell something.";
	emotion ET_SURPRISE,getnpcid(0,"King#illuvamp");
	//give quest
	completequest 14661;
	setquest 14662;
	illusion_vampire = 10;
	setpcblock PCBLOCK_ALL, 0;
	close;
}

if(illusion_vampire == 10 || illusion_vampire == 11){
	if(!isbegin_quest(14663)){
		mes "[Dracula]",
			"What could King be smelling now?";
		close;
	}
	mes "[Dracula]",
		"A fight? Oh no, we'd better hurry!";
	close;
}

if(illusion_vampire == 12 || illusion_vampire == 13){
	mes "[Dracula]",
		"I've decided to wait for her. I could use some rest, anyway.";
	close;
}

if(illusion_vampire == 14){
	mes "[Dracula]",
		"The bat blood she drinks sometimes causes her to go out of her mind. She calms down after a while, but if the people from the Church see her in that vulnerable state, they will try to kill her";
	close;
}

end;

OnInit:
	questinfo 14662,QTYPE_QUEST,1;
	setquestinfo_req 14662,14661,1;
end;
}

// =========================
//	End Found Jojo
// =========================


// =========================
//	Crafting
// =========================
gef_dun01,139,228,4	script	Great Merchant#illuvamp	900,{
	disable_items;
	disable_command;
	.@npc$ = "[Great Merchant]";
	mes .@npc$,
		"Adventurer, do you have Illusion Stones? If you have a weapon, or a piece of armor at Refining Level " + .reqRefine + " or higher, or an accessory, than I can exchange it for something better at the cost of some Illusion Stones and other materials.";
	next;
	mes .@npc$,
		"Check the catalog for available equipment and necessary materials.";
	next;
	mes .@npc$,
		"So, what do yo want?";
	next;
	switch(select("Weapon Exchange", "Armor Exchange", "Accessory Exchange", "Check the catalog", "What are Illusion Stones?", "Can I refine the equipment I get in exchange?")){
		case 1: // Weapon Exchange
			for(.@i=0;.@i<getarraysize(.illuWeapons);.@i++)
				.@menu$ += getitemname(.illuWeapons[.@i]) + ":";
			.@o = select(.@menu$) - 1;
			mes .@npc$,
				getitemname(.illuWeapons[.@o]) + .illuWDesc$[.@o] + " Let's see what you've got.";
			next;
			getinventorylist();
			for(.@i = 0; .@i < @inventorylist_count; .@i++){
				if(@inventorylist_id[.@i] != .illuWeaponsReq[.@o] || .reqRefine > @inventorylist_refine[.@i]){ 
					continue;
				}
				.@index = .@i;
				.@weapon_check = 1;
			}
			mes .@npc$;
			if(!.@weapon_check){
				mes "Let's see... Mm? What did you bring? Come back equipped with a +" + .reqRefine + "<ITEM> " + getitemname(.illuWeaponsReq[.@o]) + "<INFO>" + .illuWeaponsReq[.@o] + "</INFO></ITEM>";
				close;
			}
			
			explode(.@data$,.illuWeaponsReq2$[.@o],",");
			for(.@i = 0; .@i < getarraysize(.@data$); .@i++){
				explode(.@citem$,.@data$[.@i],":");
				if(countitem(atoi(.@citem$[0])) < atoi(.@citem$[1])){ 
					.@missing += 1;
					mes "^0000FF"+.@citem$[1]+ " " +getitemname(atoi(.@citem$[0]))+"^000000";
				}
			}
			
			if(.@missing > 0){
				mes "You're missing these items..";
				close;
			}
			
			mes "Let me warn you kid. You will lose all cards equipped on your weapon once I exchange it. Do you agree with that?";
			next;
			if(select("I agree.:I decline.") == 2){
				mes .@npc$,
					"Alright kid, come once you changed your mind.";
				close;
			}
			delitem2 @inventorylist_id[.@index],1,@inventorylist_identify[.@index],@inventorylist_refine[.@index],@inventorylist_attribute[.@index],@inventorylist_card1[.@index],@inventorylist_card2[.@index],@inventorylist_card3[.@index],@inventorylist_card4[.@index]; 
			for(.@i = 0; .@i < getarraysize(.@data$); .@i++){
				explode(.@citem$,.@data$[.@i],":");
				delitem atoi(.@citem$[0]),atoi(.@citem$[1]);
			}
			mes .@npc$,
				"Here is your Weapon.";
			getitem .illuWeapons[.@o],1;
			close;
			
		case 2: // Armor Exchange
			for(.@i=0;.@i<getarraysize(.illuArmor);.@i++)
				.@menu$ += getitemname(.illuArmor[.@i]) + ":";
			.@o = select(.@menu$) - 1;
			mes .@npc$,
				getitemname(.illuArmor[.@o]) + .illuArDesc$[.@o] + " Let's see what you've got.";
			next;
			getinventorylist();
			for(.@i = 0; .@i < @inventorylist_count; .@i++){
				if(@inventorylist_id[.@i] != .illuArmorReq[.@o] || .reqRefine > @inventorylist_refine[.@i]){ 
					continue;
				}
				.@index = .@i;
				.@weapon_check = 1;
			}
			mes .@npc$;
			if(!.@weapon_check){
				mes "Let's see... Mm? What did you bring? Come back equipped with a +" + .reqRefine + "<ITEM> " + getitemname(.illuArmorReq[.@o]) + "<INFO>" + .illuArmorReq[.@o] + "</INFO></ITEM>";
				close;
			}
			
			explode(.@data$,.illuArmorReq2$[.@o],",");
			for(.@i = 0; .@i < getarraysize(.@data$); .@i++){
				explode(.@citem$,.@data$[.@i],":");
				if(countitem(atoi(.@citem$[0])) < atoi(.@citem$[1])){ 
					.@missing += 1;
					mes "^0000FF"+.@citem$[1]+ " " +getitemname(atoi(.@citem$[0]))+"^000000";
				}
			}
			
			if(.@missing > 0){
				mes "You're missing these items..";
				close;
			}
			
			mes "Let me warn you kid. You will lose all cards equipped on your armor once I exchange it. Do you agree with that?";
			next;
			if(select("I agree.:I decline.") == 2){
				mes .@npc$,
					"Alright kid, come once you changed your mind.";
				close;
			}
			delitem2 @inventorylist_id[.@index],1,@inventorylist_identify[.@index],@inventorylist_refine[.@index],@inventorylist_attribute[.@index],@inventorylist_card1[.@index],@inventorylist_card2[.@index],@inventorylist_card3[.@index],@inventorylist_card4[.@index]; 
			for(.@i = 0; .@i < getarraysize(.@data$); .@i++){
				explode(.@citem$,.@data$[.@i],":");
				delitem atoi(.@citem$[0]),atoi(.@citem$[1]);
			}
			mes .@npc$,
				"Here is your armor.";
			getitem .illuArmor[.@o],1;
			close;
			
		case 3: // Accessory Exchange
			for(.@i=0;.@i<getarraysize(.illuAccessory);.@i++)
				.@menu$ += getitemname(.illuAccessory[.@i]) + ":";
			.@o = select(.@menu$) - 1;
			mes .@npc$,
				getitemname(.illuAccessory[.@o]) + .illuAcDesc$[.@o] + " Let's see what you've got.";
			next;
			getinventorylist();
			for(.@i = 0; .@i < @inventorylist_count; .@i++){
				if(@inventorylist_id[.@i] != .illuAccessoryReq[.@o]){ 
					continue;
				}
				.@index = .@i;
				.@weapon_check = 1;
			}
			mes .@npc$;
			if(!.@weapon_check){
				mes "Let's see... Mm? What did you bring? Come back equipped with a <ITEM> " + getitemname(.illuAccessoryReq[.@o]) + "<INFO>" + .illuAccessoryReq[.@o] + "</INFO></ITEM>";
				close;
			}
			
			explode(.@data$,.illuAccessoryReq2$[.@o],",");
			for(.@i = 0; .@i < getarraysize(.@data$); .@i++){
				explode(.@citem$,.@data$[.@i],":");
				if(countitem(atoi(.@citem$[0])) < atoi(.@citem$[1])){ 
					.@missing += 1;
					mes "^0000FF"+.@citem$[1]+ " " +getitemname(atoi(.@citem$[0]))+"^000000";
				}
			}
			
			if(.@missing > 0){
				mes "You're missing these items..";
				close;
			}
			
			mes "Let me warn you kid. You will lose all cards equipped on your accessory once I exchange it. Do you agree with that?";
			next;
			if(select("I agree.:I decline.") == 2){
				mes .@npc$,
					"Alright kid, come once you changed your mind.";
				close;
			}
			delitem2 @inventorylist_id[.@index],1,@inventorylist_identify[.@index],@inventorylist_refine[.@index],@inventorylist_attribute[.@index],@inventorylist_card1[.@index],@inventorylist_card2[.@index],@inventorylist_card3[.@index],@inventorylist_card4[.@index]; 
			for(.@i = 0; .@i < getarraysize(.@data$); .@i++){
				explode(.@citem$,.@data$[.@i],":");
				delitem atoi(.@citem$[0]),atoi(.@citem$[1]);
			}
			mes .@npc$,
				"Here is your accessory.";
			getitem .illuAccessory[.@o],1;
			close;
		
		case 4: // Check the catalog
			mes .@npc$,
				"Do you want to see my catalog? Sure thing.";
			next;
			switch(select("Weapons (5 kinds)", "Armor (1 kind)", "Accessory (2 kinds)")){
				case 1: // Weapons
					for(.@i=0;.@i<getarraysize(.illuWeapons);.@i++)
						.@menu$ += getitemname(.illuWeapons[.@i]) + ":";
					.@o = select(.@menu$) - 1;
					mes "<ITEM> " + getitemname(.illuWeapons[.@o]) + "<INFO>" + .illuWeapons[.@o] + "</INFO></ITEM>",
						"*****************",
						"Necessary items",
						"+"+.reqRefine+" or higher "+.illuWeaponsReq[.@o]+"x1";
					explode(.@data$,.illuWeaponsReq2$[.@o],",");
					for(.@i = 0; .@i < getarraysize(.@data$); .@i++){
						explode(.@citem$,.@data$[.@i],":");
						if(countitem(atoi(.@citem$[0])) < atoi(.@citem$[1])){ 
							.@missing += 1;
							mes .@citem$[1] + " " + getitemname(atoi(.@citem$[0]));
						}
					}
					close;
				
				case 2: // Armor
					for(.@i=0;.@i<getarraysize(.illuArmor);.@i++)
						.@menu$ += getitemname(.illuArmor[.@i]) + ":";
					.@o = select(.@menu$) - 1;
					mes "<ITEM> " + getitemname(.illuArmor[.@o]) + "<INFO>" + .illuArmor[.@o] + "</INFO></ITEM>",
						"*****************",
						"Necessary items",
						"+"+.reqRefine+" or higher "+.illuArmorReq[.@o]+"x1";
					explode(.@data$,.illuArmorReq2$[.@o],",");
					for(.@i = 0; .@i < getarraysize(.@data$); .@i++){
						explode(.@citem$,.@data$[.@i],":");
						if(countitem(atoi(.@citem$[0])) < atoi(.@citem$[1])){ 
							.@missing += 1;
							mes .@citem$[1] + " " + getitemname(atoi(.@citem$[0]));
						}
					}
					close;
				
				case 3: // Accessory
					for(.@i=0;.@i<getarraysize(.illuAccessory);.@i++)
						.@menu$ += getitemname(.illuAccessory[.@i]) + ":";
					.@o = select(.@menu$) - 1;
					mes "<ITEM> " + getitemname(.illuAccessory[.@o]) + "<INFO>" + .illuAccessory[.@o] + "</INFO></ITEM>",
						"*****************",
						"Necessary items",
						"Socketed "+.illuAccessoryReq[.@o]+"x1";
					explode(.@data$,.illuAccessoryReq2$[.@o],",");
					for(.@i = 0; .@i < getarraysize(.@data$); .@i++){
						explode(.@citem$,.@data$[.@i],":");
						if(countitem(atoi(.@citem$[0])) < atoi(.@citem$[1])){ 
							.@missing += 1;
							mes .@citem$[1] + " " + getitemname(atoi(.@citem$[0]));
						}
					}
					close;
			}
		
		case 5: //What are Illusion Stones?
			mes .@npc$,
				"What are Illusion Stone, you ask? Well... I don't think anyone knows exactly what they are.";
			next;
			mes .@npc$,
				"I only know they're rare and can only be found in some special places, and I'm here to collect them for my clients.";
			next;
			mes .@npc$,
				"My clients want to figure out what these stones are. They're paying me a lot of money.";
			next;
			mes .@npc$,
				"So I could offer adventurers like you ^0000FFexpensive equipment in exchange for the stones^000000, and still fetch a profit.";
			next;
			mes .@npc$,
				"Bring ^0000FFa piece of refined equipment, Illusion Stones^000000, and various materials that are only found in this place. ^0000FFI'll upgrade the equipment - weapon, armor or accessory^000000 - for you.";
			next;
			mes .@npc$,
				"This benefits both of us. Let me know if you're interested in my proposition.";
			close;
			
		case 6: // Can I refine the equipment I get in exchange?
			mes .@npc$,
				"So you want t reinforce the equipment you get. You're thorough. I like that!";
			next;
			mes .@npc$,
				"A while ago, an adventurer who passed through this place told me that a chemist in Prontera refines the Illusion equipment in exchange for Illusion Stones.";
			next;
			mes .@npc$,
				"It seems Illusion Stones are a popular topic everywhere. Everyone wants to know about what they are.";
			next;
			mes .@npc$,
				"If you want refine your equipment, then go to the Illusion Echanter.";
			close;
	}
	
end;
OnInit:
	.reqRefine = 7;
	setarray .illuWeapons,28022,28023,2039,18149,28612;
	setarray .illuWeaponsReq,1266,1260,1473,1727,1557;
	setarray .illuWeaponsReq2$,"25271:80,25261:20", "25271:10,25264:100", "25271:40,25267:100","25271:50,25265:100","25271:50,25262:10";
	setarray .illuWDesc$,	", huh? That's a good weapon. Dreaful name, though.",
							" It perfectly fits in this place.",
							", huh? *Chuckle* Having that is every mage's dream.",
							"... I would've loved to have this when? Sigh, never mind.",
							", huh? It's been a long time since I heard the story behind this book. Anyway,";
	
	setarray .illuArmor,20840;
	setarray .illuArmorReq,2525;
	setarray .illuArmorReq2$,"25271:30,25263:200";
	setarray .illuArDesc$,	". Someone in this place? *Ahem*";
	
	setarray .illuAccessory,28508,28509;
	setarray .illuAccessoryReq,2715,2715;
	setarray .illuAccessoryReq2$,"25271:50,25266:400","25271:50,25267:400";
	setarray .illuAcDesc$,	". *Chuckle* I remember when I was young, my friends and I wore this ring and played pranks? Hah, hah, never mind. That was a long time ago. Anyway,",
							"... It may not look like much, but it has an important meaning to me. Anyway,";
end;
}

-	script	hunt#illuvamp	-1,{
OnKillMushroom:
if((illusion_vampire == 8 || checkquest(14671) == 1) && 10 > countitem(25269)){ // TODO maybe not limit to 10?
	getitem 25269,1;
}
end;
OnKillDrainlair:
if((illusion_vampire == 8 || checkquest(14671) == 1) && 10 > countitem(25268)){ // TODO maybe not limit to 10?
	getitem 25268,1;
}
end;
}
