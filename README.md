
import discord
from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix="!", intents=intents)

@bot.event
async def on_ready():
    print(f"Bot connecté en tant que {bot.user}")

@bot.command()
async def bonjour(ctx):
    await ctx.send(f"Salut {ctx.author.name} ! 👋")

bot.run("TOKEN_ICI")
