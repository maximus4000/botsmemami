import random
import os

import requests
import discord
from discord.ext import commands

intents = discord.Intents.default()
intents.members = True
intents.message_content = True
bot = commands.Bot(command_prefix="$", intents=intents)

@bot.event
async def on_ready():
    print("Готов")

@bot.command()
async def mem(ctx):
    files = os.listdir("pytb")
    rand_mem = random.choice(files)
    with open(f"pytb/{rand_mem}", 'rb') as file:
        picture = discord.File(file)
    await ctx.send(file=picture)
@bot.command()
async def animals(ctx):
    files = os.listdir("pytb")
    rand_mem = random.choice(files)
    with open(f"pytb/{rand_mem}", 'rb') as file:
        picture = discord.File(file)
    await ctx.send(file=picture)

def get_duck_image_url():    
    url = 'https://random-d.uk/api/random'
    res = requests.get(url)
    data = res.json()
    return data['url']


@bot.command('duck')
async def duck(ctx):
    '''По команде duck вызывает функцию get_duck_image_url'''
    image_url = get_duck_image_url()
    await ctx.send(image_url)

def get_dog_image_url():    
    url = 'https://random.dog/woof.json'
    res = requests.get(url)
    data = res.json()
    return data['url']


@bot.command('dog')
async def dog(ctx):
    '''По команде duck вызывает функцию get_duck_image_url'''
    image_url = get_dog_image_url()
    await ctx.send(image_url)



bot.run("Token")
